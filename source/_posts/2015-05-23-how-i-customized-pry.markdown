---
layout: post
title: "How I Customized Pry"
date: 2015-05-23 11:20:31 -0600
comments: true
categories: pry, gem, gems, terminal
---

In this tutorial I'm going to be showing off a couple different ways that I customized [pry gem](https://github.com/pry/pry).

First of all you'll need to add a `.pryrc` file to your root directory. You can do it with this command: `touch ~/.pryrc`.

## Custom commands

Pry custom commands are a way for you to add shortcuts to each pry session to make certain commands easier or shorter to type.

The first one I set up was for the built in `play` method that pry supports. I found myself copying lines of code from `binding.pry` that I was in and pasting them line by line to see the result of the output.

The `play` command allows you to play a line of code or lines of code using a range of numbers, using the flag `-l`. Here is an example:


```
=> 1: require "pry"; binding.pry
   2:
   3: p "Hello #{name}"
   4: p "Konichiwa #{name}"
   5: p "Hola #{name}"
   6:

[1] pry (main)> play -l 3
NameError: undefined local variable or method `name' for main:Object
from (pry):1:in `<main>'

[2] pry (main)> name = "travis"
=> "travis"

[3] pry (main)> play -l 3
"Hello travis"
=> "Hello travis"

[4] pry (main)> name = "Solid Snake"
=> "Solid Snake"

[5] pry (main)> play -l 3..5
"Hello Solid Snake"
"Konichiwa Solid Snake"
"Hola Solid Snake"
=> "Hola Solid Snake"
```


How do we make a shortcut for this? Pry supports adding block commands to your `.pryrc`. I wanted to make it slightly easier to type `play -l` so I added this to my `.pryrc`:

```
Pry::Commands.block_command 'pl', "Alias for 'play -l'" do |lines|
  _pry_.run_command("play -l #{lines}")
end
```

The `Pry::Commands.block_command 'pl'` says to make a command with the name 'pl'.  
The `"Alias for 'play -l'"` is a description of the command.  
You can have the method take parameters with `do |lines|`.  
The middle portion `_pry_.run_command` says to use the current pry instance to run a pry command.  
And then we tell it to run the `play -l` command with a line or range of lines.

Now in our example we can do:

```
=> 1: require "pry"; binding.pry
   2:
   3: p "Hello #{name}"
   4: p "Konichiwa #{name}"
   5: p "Hola #{name}"
   6:

[1] pry (main)> pl 3
NameError: undefined local variable or method `name' for main:Object
from (pry):1:in `<main>'

[2] pry (main)> name = "Liquid Snake"
=> "Liquid Snake"

[3] pry (main)> pl 3..5
"Hello Liquid Snake"
"Konichiwa Liquid Snake"
"Hola Liquid Snake"
=> "Hola Liquid Snake"
```

Simple right? Let's add another one that I've enjoyed using:

```
Pry::Commands.block_command /(jk)(jk)*/, "Alias for exit" do
   captures[1] ? _pry_.run_command('exit') : exit
end
```

This one is just a tiny bit more complex. I was growing tired of misspelling `exit` and tired of typing `exit!`. Here's a breakdown of the differences this command does:

The `/(jk)(jk)*/` is a regex match for 'jk' or 'jkjk'.  
`captures` is the name of the object that's created for the regex match.  
The middle line says, if the capture was 'jkjk' run the pry internal exit command. This allows you to step through breakpoints. I usually default to using `CTRL + D` though to obtain the same thing.  
Otherwise run the ruby version of `exit` that terminates the currently running instance, which is the same as `exit!`.



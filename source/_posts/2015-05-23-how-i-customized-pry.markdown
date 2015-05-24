---
layout: post
title: "How I Customized Pry"
date: 2015-05-23 11:20:31 -0600
comments: true
categories: pry, gem, gems, terminal
---

In this tutorial I'm going to be showing off a couple different ways that I customized the [pry gem](https://github.com/pry/pry).

You'll need to add a `.pryrc` file to your root directory. You can do it with this command: `touch ~/.pryrc`.

## Block Commands

Pry block commands are a way for you to add shortcuts to every pry session.

The first one I set up was for the built in `play` method that pry supports. I found myself copying lines of code from a `binding.pry` breakpoint that I was in and pasting them line by line to see the result of the output. This can be slow and painful when there's a lot of code in a method.

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

This is where block commands come in to play. I wanted to make it slightly easier to type `play -l` so I added this to my `.pryrc`:

```
Pry::Commands.block_command 'pl', "Alias for 'play -l'" do |lines|
  _pry_.run_command("play -l #{lines}")
end
```

`Pry::Commands.block_command 'pl'` says to make a command with the name 'pl'.  
`"Alias for 'play -l'"` is a description of the command.  
You can have the method take parameters with `do |lines|`.  
`_pry_.run_command` uses the current pry instance to run a pry command.  
And then we tell it to run the `play -l` command with a line or range of lines.

*Note: the code within the block is actually plain ruby code*

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

Simple right? Here's another one that I've enjoyed using:

```
Pry::Commands.block_command 'jk', "Alias for 'exit!'" do
  exit
end
```

With this command I can type `jk` to exit in the same way that you can type `exit!`. Combined with using `CTRL + D` to step through breakpoints it feels nice and quick to enter a binding, check a variable, jump to a different breakpoint to check it again and exit out.


## The Edit Command and Your Default Editor

The `edit` command is super useful for quickly editing code in a heavy pry session without losing possible variables or methods. Here's how to setup your default editor, simply replace "vim" with the editor of your choice:

`Pry.config.editor = "vim"`

Here's an example of using edit:

```
[1] pry (main)> def hello
[1] pry (main)*   puts "Hello"
[1] pry (main)* end
=> :hello
[2] pry (main)> edit hello
```

Vim opens for editing:

```
1 def hello
2   puts "Hello"
3 end
```

We add a line of code:

```
1 def hello
2   puts "Hello,"
3   puts "Mr. Bond"
4 end
```

After saving and closing Vim, we return back to pry:

```
=> :hello
[3] pry (main)> show-source hello

From: (pry) @ line 4:
Owner: Object
Visibility: public
Number of lines: 4

def hello
  puts "Hello,"
  puts "Mr. Bond"
end

[4] pry (main)> hello
Hello,
Mr. Bond
=> nil
```

## Prompt Name

This command can be used in combination with having a `.pryrc` in each project folder that you're working on. This would let you see the project name as your pry prompt like so:

`[1] my_project (main)>`

Otherwise, if you use the `.pryrc` in your root directory, it'll be applied globally. I decided I wanted to make pry look a little more awesome so I stuck an emoji in there. Here's the command you use:

`Pry.config.prompt_name = "🙏 "`

*Note: I put an extra space on the end so it's centered.*

Now my prompt looks like this:

```
[1] 🙏(main)> def pray
[1] 🙏(main)*   puts "let's hope this works"
[1] 🙏(main)* end
=> :pray
[2] 🙏(main)> pray
let's hope this works
=> nil
[3] 🙏(main)>
```

## That's It

I'm continuing to try and find ways to customize pry further to improve productivity or make it look awesome. If you're interested in other ways you can customize pry, check out their [guide on github.](https://github.com/pry/pry/wiki/Customization-and-configuration)

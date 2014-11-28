---
layout: post
title: "Change Your iTerm Prompt to Emoji"
date: 2014-11-23 16:52:58 -0700
comments: true
categories: iterm, vim, terminal, themes, schemes
---

Hello and welcome to my tutorial on how to further
customize your iTerm. This tutorial follows
[my previous tutorial](http://yoderbacon.com/blog/2014/10/22/how-to-customize-iterm/)
on how to customize the colors and background of iTerm to
make it more visually pleasing.  

In this tutorial we are going to change our prompt to
have an emoji instead of a dollar sign ($), which can
be seen in the following screenshot.

When we left off in the last tutorial we ended up with
a terminal window similar to this:


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/source/source/_posts/images_change_prompt/1_before.png 600 'Still awesome!' %}


## Let's do that change thing!

The first thing you're going to want to do is open your
bash profile. I'm also assuming you have one made already
are, at least, mildly aware that it exists. Open up iTerm
and navigate to your root directory. If terminal hasn't
opened in your root directory the easiest way to get
there is to type `cd` in and push enter.

From your root directory, open up your bash profile in
Text Edit, the built in Mac text editor. The simple way
to do this is to type:
`open .bash_profile`
in your terminal. You should get something like the
following:


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/source/source/_posts/images_change_prompt/3_open_bash.png 700 'So scary!' %}


In this file you're going to look for `\$`. For me it was
at the bottom of the file. You can also find it doing a
search with `⌘+F`.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/source/source/_posts/images_change_prompt/4_text_edit_dollar.png 700 'Did you find it?' %}


Once you find it, highlight the leading escape \ and the
$. Then open up the Apple special characters
menu with `^ ⌘ Space` or by finding it at the bottom of
the edit menu.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/source/source/_posts/images_change_prompt/5_special_characters.png 700 'Did you find it?' %}


This will open up the built Apple menu with special
characters and emoji. Here you can select any emoji
you'd like, but, obviously, pizza is the best emoji
and it'll be the one I'll be selecting.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/source/source/_posts/images_change_prompt/6_special_pizza.png 700 'My spirit animal.' %}

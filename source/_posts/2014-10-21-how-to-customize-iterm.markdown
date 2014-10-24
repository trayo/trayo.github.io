---
layout: post
title: "How to Customize iTerm"
date: 2014-10-04 20:12:24 -0600
comments: true
categories: iterm, vim, terminal, themes, schemes

---

Hello!  
Welcome to my tutorial on customizing iTerm!
In this tutorial I'm going to show you the basics of importing color schemes,
customizing those schemes and setting up a background. The shot below is our
destination final product.

{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/20_final_shot_fullscreen.png 850 'So awesome!' %}


## Let's get started!

Here's what my terminal looked like when I started, with a shot of vim for good measure:

{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/1_term_default_vim.png 350 'So boring!' %}
{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/2_term_default.png 375 'Kind of cool, but still not super cool.' %}


A quick [google search](http://goo.gl/Y1A32Q) will show some
results for awesome color schemes already made by the community.  
We're going to use the schemes available at [iterm2colorschemes.com](http://iterm2colorschemes.com/)
since they have a bunch of ready made schemes available.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/3_theme_examples.png 400 'Mathematical!' %}


When you find one you like we're going to clone
[the repository](https://github.com/mbadolato/iTerm2-Color-Schemes) off of Github. The files
aren't very large and you'll have them readily available for quickly switching between colors.


{% img top http://i.imgur.com/N1p1G40.png 400 'ALL THE THINGS' %}


Open up that terminal and navigate to a directory where you would like to clone the repo.
I used my Documents folder.


```
$ cd Documents/  
$ git clone https://github.com/mbadolato/iTerm2-Color-Schemes  
```


Still in terminal, open up preferences. This can be done either one of two ways:  
from the menu bar under iTerm > Preferences  
or use the keyboard shortcut ( ⌘ + , ) .


Once you're in the preferences window, click on the *profiles* button.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/4_preferences.png 800 %}


Then click on the *colors* tab.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/5_profiles.png 800 %}


## Importing colors!


At the bottom there is a *load presets* button that will let us import the color themes
that we cloned.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/6_profiles_color_tab.png 800 %}


In the little drop down window click *import*.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/7_profiles_color_import.png 800 %}


Choose the theme that you would like to import. You can import as
many as you like, but you don't need to import all of them. I chose by looking at
[iterm2colorschemes.com](http://iterm2colorschemes.com/) and making a list of the
ones that caught my eye and trying each one out.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/8_file_itermcolors.png 800 %}


The theme you choose will then appear in the *load presets* drop down where you can select it.
It should reflect immediately because we are working on the default profile.


##If it didn't work right away:


If for some reason it didn't update immediately, exit preferences and open up the profile
chooser by hitting ( ⌘ + i ). You will get the following window.  


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/17_command_eye.png 500 %}


Select the profile that you are working with. If you didn't create a profile, then your
profile will be the one available called *default*. Then choose *change profile*.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/18_change_profile.png 600 %}


Now we should see our colors change! Woo!


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/10_still_pink.png 400 %}


## Customize a little more!


In the *colors tab* in *preferences* there are some color boxes that change the overall
colors. The background box here is used you want to change your background color, but at the
bottom of the tutorial I will show you how to select a wallpaper instead of having a
plain solid color for a background.  


The bar for me that is pink with the time on it didn't change and doesn't quite match the rest
of the colors in the scheme so it becomes a prime candidate.  


The colors back on *preferences* correspond directly to what is seen on screen.
Of the two magenta boxes, the one I want is on the left. When you click it you get the following
window.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/files/source/_posts/images_customize_iterm/11_change_magenta.png 800 %}


The tabs at the top of this window have some different ways to pick colors. I used the
color wheel, but the color palette tab in the middle is an awesome source too.  


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/master/source/_posts/image_source_2014-10-04/9_under_middle_line.png 400 %}


If you use the color wheel, I recommend keeping the arrow on the bar to the right of the color
wheel slightly under the middle line, but it will vary based on your preferences and scheme.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/master/source/_posts/image_source_2014-10-04/10_new_bar_color.png 400 %}


Again, if for some reason it didn't update immediately, open up the profile chooser by hitting
( ⌘ + i ) and click the *change profile* button.


{% img top https://raw.githubusercontent.com/trayo/trayo.github.io/master/source/_posts/image_source_2014-10-04/15_change_profile.png 400 %}

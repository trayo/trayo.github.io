---
layout: post
title: "Jump and Delete Words in iTerm"
date: 2016-05-18 20:51:59 -0700
comments: true
categories: iTerm keyboard shortcuts delete word words jump
---

I really feel like I'm missing out on being able to jump words when working in terminal and found some blogs on how to do it by using `option`. I tried it for a while and found the `option` key to be placed in such a weird position on the Apple keyboards that I wouldn't use `option` and often forget about it while in the "programming zone".

I'm already used to using `ctrl + f` and `ctrl + b` to move the cursor forward and backward in terminal and, instead of `option`, decided to give `ctrl + shift` a try. I found this to be easier to use given the placement of `capslock` (which should be your `ctrl`!) and `shift` on the keyboard, compared to `option`.

If you use `ctrl + b` and `ctrl + f` to navigate cursor, I recommend give these steps a try. If you don't use those keyboard shortcuts they will take time to get used to, but I like them particularily because I don't have to lift my hands off of home row to reach the arrow keys.

## How To Use Ctrl + Shift + f and Ctrl + Shift + b To Jump Words

To assign the shortcut open the iTerm preferences and choose the `keys` tab. Select the `+` button at the bottom to add a new shortcut. In the `Keyboard Shortcut` field, push the keys `ctrl + shift + b` or `ctrl + shift + f` and you should see something like `^⬆︎B` or `^⬆︎F`. Then, in the `Action` dropdown, select `Send Escape Sequence` and enter the same letter (`b` or `f`) as the keyboard shortcut you entered.

Do it for the other key and that's all there is to it!

## How To Assign Ctrl + Shift + Delete To Delete Whole Words

Assign a keyboard shortcut, in the same way as above, and use `ctrl + shift + delete` as the `Keyboard Shortcut`. Then for the `Action` select `Send Hex Code` and use the code `17` in the field.

## How To Assign Option

Optionally, if you still want to use `option` instead of `ctrl + shift`, you can use `option + ⟵` and `option + ⟶` when assigning the keyboard shortcut to jump words and `option + delete` when assigning the keyboard shortcut for deleting words.


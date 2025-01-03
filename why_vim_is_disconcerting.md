---
title: "Why Vim Is Disconcerting"
date: '2021-09-03'
---

Vim.

A word that sparks equal measures of fear and delight into the hearts
and minds of the hacker community. A text editor that inspires the same
unreasonable degree of primal emotion as Marmite: you either love it or
hate it.

On the one hand, you may already think that you know how to edit text on
a computer, and you might therefore think there's no need for any
explanation here. After all, how hard can it be?

On the other hand, you might already bear the psychological scars of
having been plunged into the counter-intuitive world of vim without
adequate preparation.  Perhaps you tried to `git commit`, and Git then
assumed that Vim was the right text editor for you to write your commit
message. And it is infamously difficult for a novice to work out
how even to quit Vim.

So let's get that out of the way. If you're using the terminal, and
suddenly find that some command had opened Vim for you, and you just
want to escape, then all you need to do is press these keys:

```
:q!
```

The colon `:` will put you in command mode; the `q` will tell Vim that
you wish to **q**uit; and the exclamation mark `!` will make clear that
yes, you do want immediately to quit, whether or not you've made changes
to the file, or saved them.

And with that first bit of Vim advice, we have already touched on Vim's
use of different **modes**, which is perhaps the primary thing which 
differentiates Vim from the text editors and word processers that you
may be used to.

Before using Vim my experience of text editing on a computer was mainly
confined to Microsoft Word or Google Docs, or maybe Notepad when I 
wanted to write code that didn't get reformatted when it was saved.

So I assumed that the default, and indeed constant and single
mode of a text editor should be the *insert* mode. You open your word
processer, you press some keys on the keyboard, and the pressed
characters follow your flashing cursor across the screen.

For commands that weren't immediately concerned with inserting
characters, you used the mouse to select some function from a menu at
the top of the screen (or wherever). If you were a real text-editing
wizard then you might remember the shortcut for a specific
command, to save you taking your hands off the keyboard. Maybe CTRL-S to
save the file, or ALT-F to open the whole list of file-related commands.

And that was basically it.

The most disconcerting difference with Vim is that although it is
commonly considered a text *editor*, its default 'normal mode' is not
text insertion but text navigation. This is initially surprising: you
open the text editor and find that it won't let you insert any text!
Until you realize that you just need to press the `i` key, to enter
'insert mode'.

So why does Vim not start in 'insert mode'? And, depending on what
version of Vim you are using, and how things are configured, you might
find that the arrow keys don't even work to let you navigate around in
normal mode. How can this be 'normal mode' if Vim doesn't even let me 
move normally!

Ah, you see in Vim, you don't need arrow keys, you just use the `h`,
`j`, `k`, and `l` keys that your touchtyping fingers are closest to.
Which saves you not only from having to waste time and energy moving 
your hand from keyboard to mouse, but even from moving your fingers away
from the keyboard's home row. It takes a few minutes of practising on
Vim's `:Tutor` (or you could just [play
`rogue`!](https://playclassic.games/games/role-playing-dos-games-online/play-rogue-online/play/)),
but once the Vim arrow key-bindings have been installed in your fingers'
muscle memory, I doubt you will want to go back.

But there's more to the joy of navigating text in Vim than just a more
efficiently positioned set of arrow keys. There's a whole composable
language of how to move around. And this is where the genius of not
always being in 'insert mode' begins to emerge. Because you can press a
key without causing a character to be inserted means that you now have a
whole keyboard of potential shortcuts, which don't even require
simultaneously holding CTRL, or ALT, or any of those other super-powered
keys around the corners of your keyboard.

So in normal mode, you can press `w`, and Vim will take you to the
beginning of the next **w**ord. Press `b` and Vim will take you **b**ack
to the beginning of the previous word. Don't want the beginning of a
word? Press `e` and you can go to the **e**nd of the word.

These little shortcuts then combine to form a whole language. If you
want to delete something, then `d` is for delete -- but what do you want
to delete? Everything until the end of the word? Then press `d` then
`e`. Everything until the end of the third word from your cursor? That
would be `d` then `3` then `e`.

Or you could press `v` to enter 'visual mode', press `3e` to navigate to
the end of the 3rd word, then move one letter to the left with `h`, and
then press `d` to delete the highlighted selection.

The basics are not that complicated. Give yourself half an hour to play
through Vim's `:Tutor`, and then just start using it. If you get stuck
you can always **w**rite your file to disk (ie. 'save') with `:w`, and
then if absolutely necessary switch back to Notepad!

And then once you understand the basics, you can start configuring your
`.vimrc` (or perhaps Neovim's `init.vim`) and install some plugins. We
can talk about that another time.

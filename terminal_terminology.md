---
title: Terminal Terminology
date: '2020-01-03'
tags: ['terminal', 'coding']
---

So last time I made the case for why you should stop relying on your
mouse pointing and clicking on things, and learn to actually speak to
your computer in language. And speaking of language, I thought I should
add a note on *terminol*ogy:

- a *terminal* is an endpoint. Railways and aeroplanes have terminals.
  [Tom Hanks spent a movie](https://www.youtube.com/watch?v=iZqQRmhRvyg)
  stuck inside in one. A computer *terminal* is called thus not because
  Tom Hanks once opened `vim` and has not yet worked out how to escape
  (`:q!`, but we'll come to that another time), but because before there
  were graphical windows for different apps, the video display of the
  computer monitor was the *endpoint* for data coming from the computer
  mainframe. And now *terminal emulators* are apps which reproduce that
  simple classic experience of interacting with the out-of-sight
  computational cogs through simple (or not-so-simple) text.

- the *shell* is then the program that runs with the terminal display to
  actually allow you to interact with the files and folders on your
  computer. I suppose it's called the shell because it is/was the
  outermost layer of the computer's operating system.

- the *command line* is then the line on which you type commands into
  the terminal to interact with the shell.

So you can now see why the terms terminal, shell, and command line often
seem synonymous. But also that they are slightly, subtly different.

It's also worth remembering that as well as being able to engage with
the shell interactively, by typing commands one-by-one, and then having
the results evaluated and printed (the read-evaluate-print-loop is
sometimes called the REPL), you can also save your commands to a file
and then run the `sh`ell program on that file to implement those
instructions. Like an [actor *interpreting* a
script](https://www.youtube.com/watch?v=ZtXJldfVQJs).

And so we come to scripting languages. But that can wait until next
time.

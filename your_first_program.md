---
title: 'Running Your First Program'
date: '2020-03-06'
tags: ['coding', 'bash', 'python', 'terminal']
---

I promised that I would teach you the magical art of writing scripts for
your computer to perform. And in the next few hundred words, I intend to
fulfil that promise. But I must teach you not only how to play the part
of a screenwriter writing scripts, but also of a producer actually
making sure the script is acted out successfully. And while in Hollywood
these different roles might be labelled 'screenwriter' and 'director',
in the world of tech they are called #dev and #ops. Put them together
and you get #devops.

First, let's start with `bash`. We already know how to engage
interactively with the REPL. Now let's write an actual script. And
following in the noble tradition of hackers everywhere, it's going to be
the apparently trivial command for the computer to print the words
"Hello World". In `bash`, all you need is a script that says:

``` bash
echo Hello World
```

So you could open up your favourite text editor, type those words, and
save the file as `hello.sh`. Or you could just use the `>` operator to
redirect the output of the `echo` command to a file without bothering
with a text editor: 

``` bash
echo 'echo Hello World' > hello.sh 
```

You might want to use a text editor to check that your file does say
`echo Hello World`. Now when you're ready, you can run the program
with `bash hello.sh`. And it should produce the global greeting
you've been awaiting.

``` 
Hello World
```

But I've lied to you. I've said that with `bash hello.sh` you would run
the program you've just written. But what's actually happened, is that
you've run `bash`, which has interpreted the instructed contained in the
`hello.sh` script and executed them. So what we really should do is
modify the permissions of the file to add e**x**ecution rights:

``` bash
chmod +x hello.sh
```

And now you'll be able to actually run it directly as a program in its
own right:

``` bash
./hello.sh
```

So now you can write programs in `bash`. Next time we'll learn some
other languages...

<script async data-autoplay="true" data-loop="true" data-speed=3
id="asciicast-VwgzprpJQNAOdiq2fKmwRzS2q" 
src="https://asciinema.org/a/VwgzprpJQNAOdiq2fKmwRzS2q.js"></script>



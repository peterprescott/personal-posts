---
title: "Compile Your Code"
date: '2020-11-06'
---

Perhaps my [Nintendo-themed diversions](mario_shells.html) have given
you the impression that I'm not a sober and serious software engineer,
but just some sort of script kiddie. 

Well, today I intend to prove my mettle, by demonstrating the dark art
of actually compiling code. And rather than mess around with any of
those new kids on the block like Go or Rust, we'll be learning to speak
in the venerable language of C, which is still -- according to the cheat
sheet on [learnxinyminutes.com](https://learnxinyminutes.com/docs/c/) --
<q>**the** language of modern high-performance computing</q>.

Unlike our previous examples in [Bash](your_first_program.html) and
[Python](now_in_python.html), the code is probably now too complex to
just be `echo`ed straight into a file, so start by opening your
favourite text editor, and then write this:

``` c
#include <stdio.h>

int main() { 
  printf("Hello World!\n"); 
  return 0; 
} 
```

Save the file as `hello.c`, and then we'll compile it with `gcc` (which
once stood for 'GNU C Compiler', but now includes functionality for
various other compiled languages, meaning the acronym has been adjusted
to 'GNU Compiler Collection'). If that's not already on your system,
then you can find installation instructions [on the
website](https://gcc.gnu.org/install/).

Then run `gcc hello.c -o hello` to compile the code in your `hello.c`
file and **o**utput into a ready-to-run `hello` executable binary.

Check that it runs: `./hello` -- and you and the world should be
greeted. And then you can use the `time` command to compare its speed to
the Bash and Python scripts we wrote previously.

---
title: "On Your Marks, Git Set..."
date: '2021-01-05'
---

It's taken longer than I initially planned to come to the point where
I'm ready to initiate you into the secret arts of git wizardry, but I
think we're now ready. We've learned how to *speak computer* and use the
terminal instead of just clicking your cursor, and how to write and
execute programs, even when it requires compiling your code.

So, `git` ready for a series of terrible puns where I pretend that the
'e' in get and the 'i' in git are indistinguishable.

To begin with, let's install the program:

```
sudo apt install git
```

Or if you're not using Debian, you should be able to [find some
installation instructions here](https://git-scm.com/downloads).

Check you've installed it successfully and can run it from the
command-line, just by checking the version:

```
git --help
```

And you should see a list of the common Git commands. Let's use a few of
them.

Say we had a folder with our hello_world scripts:

```
mkdir hello_world
cd hello_world
echo 'echo "Hello World"' > hello_world.sh
echo 'print("Hello World")' > hello_world.py
```

Then we can initialize Git version control just like this: `git init`.

And you should get a message telling you that you have "Initialized
empty Git repository".

Now you ask for the `git status`, and you will be told that you have
'No commits yet', but there are 'Untracked files'. So let's add them!
Just one at a time, so we can see what happens.

Let's start with the Bash script: `git add hello_world.sh`. Now if you
check the `git status`, you will be told there is a "new file" with
"changes to be committed". But those changes aren't 'committed' yet,
because `git add` just 'adds' it to the 'stage'. Which means if you `git
reset hello_world.sh` then you'll go back to having two untracked files
and no commits. But if you `git add` the file to the staging area and
then `git commit -m "Add Hello World Bash script"`, then when you ask
for your `git status` it will no longer complain that you have "No
commits yet". Which means you can look at the `git log` and see the
record of your Bash script being added to the repository.

Now do the same for the other file: `git add hello_world.py`; `git
commit -m "Add Hello World Python script"`. 

And you've got both files committed to version control. Which means now
we can do something crazy: we can edit our code, without fear of
breaking things irreparably. First let's checkout a new branch: `git
checkout -b my-new-branch`. And then let's overwrite our Python script
with a more expansive greeting: `echo 'print("Hello Universe")' >
hello_world.py`. You run it, `python hello_world.py`, and if you haven't
got those double and single quotes tangled up, then you might get the
desired cosmic greeting. So now you `git add hello_world.py` to the
branch's stage, `git commit -m "Make greeting more inclusive"`, and then
you can `git checkout master`.

Pause to see that the `master` branch currently has the old greeting. If
you `git checkout my-new-branch` you can find it again. But now `git
checkout master`, and then merge the changes from your branch:
`git merge my-new-branch`.

And now you're using version control like a professional software
engineer. Next time I'll talk about GitHub, and things will get even more
exciting.

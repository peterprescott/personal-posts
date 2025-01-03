---
title: "A Python's Environment"
date: '2022-05-06'
---

The python is a snake that lives in rainforests, and other tropical
environments. But that is not the sort of python or the sort of
environment which we will be talking about today. 

The Python which will be the subject of our conversation is the computer
language which is in fact not named after the snake, but after [the
British comedy group](https://en.wikipedia.org/wiki/Monty_Python)
responsible for [the spam
song](https://www.youtube.com/watch?v=ycKNt0MhTkk) which gave us the
word we now use for [unwanted
email](https://en.wikipedia.org/wiki/History_of_email_spam). And the
environment in which that Python lives is 'on a computer'.

So we need to talk about your computer's `$PATH`, which is basically the
list of places your computer looks for a program it has been told to
run. Let's see what's in it:

```
> echo $PATH

/sbin:/bin:/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/sbin
```

Depending on how you've set up your shell config, you might have more
than this, but your system default should include all these six folders,
which we have separated by colons. Look closer and we see that they are
all `bin` (for 'binary') or `sbin` ('system binary') folders: in the
root `/` directory, the `/usr` directory, and the `/usr/local`
directory. You can read the Linux manual entry about the file hierarchy
for more information about the logic that informs which directory a file
should be in: `man hier`. Or we can use `grep` if you just want to see
the lines which mention `bin`: `man hier | grep 'bin'`.

Now we come to Python. If you can run Python from your command-line, it
is because the system can find the executable file in its `$PATH`. In
my case, running `python` returns an error: 

```
> python

zsh: command not found: python
```

I have to run `python3` to run the system version of Python. If we run
`which python3` we can see that is there in the `/bin` directory.

```
> which python3

/bin/python3
```

And just as the Linux shell has a $PATH that defines where it looks for
programs, so Python has a `sys.path` that defines where it looks for
packages you can import. Let's open the Python REPL and see what's
included:

```
> python3

Python 3.7.2 (default, Dec 31 2018, 14:25:33) [GCC 8.2.0] on linux 
Type "help", "copyright", "credits" or "license" for more information.
>>> import sys
>>> print(sys.path)

['', '/usr/lib/python37.zip', '/usr/lib/python3.7', '/usr/lib/python3.7/lib-dynload', '/usr/local/lib/python3.7/dist-packages', '/usr/lib/python3/dist-packages', '/usr/lib/python3.7/dist-packages']
```

We can use the functionality provided by Python's `os` module to see
what the other folders include:

```
>>> import os
>>> os.listdir('/usr/lib/python3.7')

['site.py', 'smtpd.py', '_collections_abc.py', 'tarfile.py', ...]

>>> os.listdir('/usr/lib/python3.7/dist-packages')

['numpy']
```

We can import modules that are in the folders in Python's `sys.path`:

```
>>> import numpy
>>> print(numpy)

<module 'numpy' from '/usr/lib/python3/dist-packages/numpy/__init__.py'>
```

But if they're not there, we'll get an error:

```
>>> import pandas

Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'pandas'
```

Now we'll talk more another time about NumPy and Pandas and the rest of
Python's data analysis toolkit, but for now we can just say that they
are examples of 'libraries' of code that are not part of the core
'standard library' installed by default. To make new code available to
Python, we just need to put it in one of the folders in `sys.path` --
and the inclusion of the empty string `''` at the start of the list
means that any modules in the directory from which you run Python are
available. Except if the library you want to add depends on other
libraries which need installing it might get slightly more complicated.

The simplest way to properly install Python packages is to use the
purpose-made tool Pip ('Pip Installs Packages'). On my Debian OS this
doesn't come installed by default, but has to be installed separately:
`sudo apt install python3-pip`. But I would actually recommend that you
don't bother, but instead use `conda` to create and manage strictly
limited Python environments that won't interfere with your operating
system's version of Python.

Conda can either be installed as 'Anaconda', which comes with the
`conda` command-line tool and 1000+ packages for scientific computing;
or as 'Miniconda', which just comes with the `conda` tool and a minimal
list of required dependencies. The official website suggests that if you
are new to Python you are better off with 'Anaconda' -- but I completely
disagree. If you are new to Python why do you need 1000+ packages for
scientific computing? So stick to Miniconda, and then you can always
download whatever other packages you want when you actually need them.

```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/install_miniconda.sh
sh ~/install_miniconda.sh -b -u -p ~/.miniconda3
rm -rf ~/install_miniconda.sh
```

You probably need to reload your shell, and you should then be able to
run `conda` from the command-line. You may also find that your shell
automatically loads Conda's `base` environment. I find this annoying, so
I disable this, by adding `auto_activate_base: false` to my [`.condarc`
configuration
file](https://github.com/peterprescott/.dotfiles/blob/master/.condarc).
Now you can create a new Python environment, with say version `3.9`:

```
conda create -n my_env python=3.9
```

Then activate it like this:

```
conda activate my_env
```

And now we can see that `conda` works its magic by adding the folders of
the activated environment, and of conda, to the system `$PATH`:

```
> echo $PATH

/home/peterprescott/.miniconda3/envs/my_env/bin:/home/peterprescott/.miniconda3/condabin:/sbin:/bin:/usr/local/sbin:/usr/local/bin:/usr/bin:/usr/sbin
```

Likewise if we open Python, and look at `sys.path`, we'll see that
the folders Python is looking in are in the directory of `my_env`. Which
means that now we can `pip install` whatever strange and wonderful new
Python packages we like, safe in the knowledge that we can remove that
Conda environment without interfering with your system's version of
Python.

```
conda remove -n my_env
```

So now perhaps you'll be able to avoid the situation described
[here](https://www.explainxkcd.com/wiki/index.php/1987:_Python_Environment).

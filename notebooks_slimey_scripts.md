---
title: "Notebooks and Slimey Scripts"
date: '2022-07-01'
---

If you want to make a Python program, what do you do?

You open your text editor, write the code, save it as `my_code.py`, and
then you can run it:

```
python my_code.py
```

But what if you want to add a little bit to your program, run that
little bit to check that it works, and then once you're sure it's
working, continue writing some more code?

(Well, you could just open another terminal window from which to run the
program --)

Or what if you wanted to write some code to read in some data, draw some
figures to begin analyzing the data, and then continue writing code
to clean the data based on the visualizations.  And you didn't want to
have to regenerate the visualizations everytime you ran the code, you
just wanted the flow of your work to remain visible later for anyone who
might be interested...

Anyway, this is kind of the idea behind writing your Python code in a
[Jupyter
notebook](https://jupyter.org/try-jupyter/retro/notebooks/?path=notebooks/Intro.ipynb).
This allows you to write chunks of code in different cells, run (or
rerun) them independently, while preserving the output of all other
cells. It is useful for any coding task that requires lots of
exploratory iteration, particularly data analysis.

To do so, install JupyterLab:

```
pip install jupyterlab
```

And then run it:

```
jupyter lab
```

You then open your web-browser (it may open automatically) and go to the
local Jupyter URL (usually `localhost:8888`; it will say in the text
printed to your terminal, after you launch Jupyter Lab). And you can
start coding!

(Aside: If you go to the official Jupyter site, you might get the
impression that Jupyter Notebook and Jupyter Lab are alternatives.
Basically Jupyter Lab is just a slightly newer interface for interacting
with Jupyter Notebooks, which gives you a file-browsing tab at the side,
and the ability to have multiple notebooks open in the same browser
window. But if you really wanted you could ignore `jupyterlab` and do
`pip install notebook` and then launch `jupyter notebook`, and apart
from those minor details it's exactly the same).

Nevertheless, there are some downsides to Jupyter Notebooks, most
clearly articulated by Joel Grus in his ['I Don't Like Notebooks'](
https://docs.google.com/presentation/d/1n2RlMdmv1p25Xy5thJUhkKGvjtV-dkAIsUXP-AL4ffI/preview?slide=id.g362da58057_0_1)
talk. He lists lots of things, but I think there are three major
problems:

1. Being able to run chunks of code independently might cause more
   trouble than it's worth: it can be more confusing to understand how
   some result was generated, as you can't later see what order all the
   code was executed in; and it encourages writing long notebooks that
   probably include obsolete code, instead of shorter, modular scripts.

2. Using Git for version control doesn't work well with the JSON format
   used to save notebook `.ipynb` files (that's an abbreviation for
   '**iPy**thon **n**ote**b**ook'). If you do want to use Git to track
   changes to your notebooks -- and you should want to use Git to track
   changes to all the code you write! -- then you should use
   [`jupytext`](https://jupytext.readthedocs.io/en/latest/index.html)
   to convert your script to a `.py` script (it can keep track of how
   your chunks of code are separated, don't worry).

3. Using Jupyter may mean you're missing out on the functionality for
   which you love your text edior or IDE. Now if you're committed to
   using Jupyter, you might be able to find
   [extensions](https://jupyterlab-contrib.github.io/migrate_from_classical.html)
   which provide that functionality. But that will take some extra
   effort.

An alternative way of being able to check if chunks of your code are
working, while just working in Vim (as [I would like to
do](./why_vim_is_disconcerting)), is to use [Tmux](./windows_in_linux)
to split the terminal window into two panes, and in the other pane run a
Python REPL. And then you can use the
[vim-slime plugin](https://github.com/jpalardy/vim-slime) to allow you
to send commands from the script you're editing in Vim straight to the
interactive Python REPL. It works for me!


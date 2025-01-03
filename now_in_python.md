---
title: 'Now The Same In Python'
date: '2020-05-01'
---

Instead of just teaching you how to write and run a program in one
language, let's do it in a few. So as to inoculate you immediately
against the idea that learning a different programming language is a
deeply difficult thing, and to instead emphasize that it's thinking in
algorithms that is the real skill.

We've already done `echo Hello World`, so that's `bash` done.

Python is similarly simple, although I suppose it's possible that you
might first need to [download Python](https://www.python.org/downloads/)
if it's not already installed on your machine.

First try running `python --version`, or if that doesn't work, `python3
--version`. If neither of those work, then follow the [instructions here
to download it](https://www.python.org/downloads/). You might then need
to restart your terminal to actually run it. Running `python` will open
the Python REPL, where you can try your first command:

``` python
print('Hello World')
```

There's a bit more punctuation here than we had in the Bash equivalent,
which could trip you up. For example, if you forget those quotation
marks ('single quotes' or "double quotes" are both fine) then you will
get a `SyntaxError`. But in fact, this makes it clearer that `print()`
is a function, which takes whatever you put inside the brackets as its
input. And the quotation marks make clearer that 'Hello World' is a
string of text. 

Now `quit()` the REPL, and write the command to a script, either by
using your favourite text editor, or by switching back to some quick
Bash to `echo 'print("Hello World")' > hello.py`. And then you'll be
able to run the script with Python: `python hello.py`.

However, if you now try modifying the file permissions so that you can
execute the program directly (`chmod +x hello.py`), you'll then get
another "Syntax error". What's going on?

Well the clue is that the spaced "Syntax error" looks suspiciously different
from the "SyntaxError" that Python gave us when we forgot to put 'Hello
World' in quotes. And the reason for that is that it's not Python that
is throwing the error, because although the `.py` file-extension is
strongly suggestive of what language the program is written in, it's
actually completely ignored by the computer, and so it's trying to
interpret the script with Bash, just as it did with our `hello.sh`
script from last time.

To specify what program to run the script through, we add a line at the
top with a [shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)), like
this: `#! python3`. Or more properly, we should perhaps write `#!
/usr/bin/env python3` so specify that it should use whatever version of
Python is being used by the
[environment](https://docs.python.org/3/library/venv.html) you are in.

But we'll talk about *environmental issues* another time.

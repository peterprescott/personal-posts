---
title: 'A Fullstack Starter App'
date: '2023-09-05'
---

A **full-stack** web application includes:

- a front-end user interface;
- a back-end API;
- a database;
- the systems and services keeping those running;
- and the repository of code for all of these components.

Even a simple app therefore involves several technological pieces:

- HTML, CSS, and Javascript for the front-end;
- a programming language for the backend;
- SQL for the database;
- some shell scripting (probably Bash) to get everything in place and running on its system;
- and Git for version control.

Last year I was at a [hackathon](https://kingdomcode.org.uk/build/)
trying to get involved with a project to help
foodbanks track their inventory so that they could more efficiently and
effectively minister to those in need--

But for some reason the code for the project wasn't open-source, and so
after more than an hour of trying and failing to get access to some of
its pieces, I gave up.

And I thought, wouldn't it be nice to have a simple fullstack skeleton
app that a project like that could build on. Open-source, so that anyone
who wanted could immediately clone the code and get involved; and it
would be nice also if it could then be put into production simply and 
cheaply, maybe even freely... It would need some sort of user
authentication, and then some minimal CRUD (Create/Read/Update/Delete) 
data management functionality.

I made an initial attempt at putting something together then and there,
but didn't get all that far. Anyway, in the last week or two I've tried
again. Python for the backend, vanilla Javascript for the frontend, a
little SQLite file for the database. And you can deploy it for free,
using PythonAnywhere for the backend, and Netlify for the front.

I'm sure it could be improved in all sorts of ways, but I'm quite
pleased with it.

If you're a developer, then you can clone this repo and get started:

```
git clone https://github.com/peterprescott/fullstack
cd fullstack
conda create --name fs_env python=3.10
conda activate fs_env
cd py_setup
pip install -r requirements.txt
cd ..
python run.py
```

That run script should set up two threads: one to serve a front-end user
interface at [localhost:8000](http://localhost:8000), and the other to
run a back-end API at [localhost:5000](http://localhost:5000).

While you're getting that working, you should also be able to find a
working demo of the app [here](https://fullstack.me.uk/).

---
title: "Branches, Forks, and Clones"
date: '2021-05-07'
---

Before you begin I want to close your eyes and imagine a battalion of
storm-troopers (they being a *clone* army) in the forests of Endor (lots
of trees meaning lots of *branches*), sitting down on picnic blankets,
and all holding those plastic green *forks* that my mum would pull out
for that sort of occasion...

Or not. Anyway, today I will continue talking about Git, and attempt to
explain the nature and function of branches, forks, and clones.

Branches we have already met. When working in your own local (ie.
on-your-own-machine) repository, you can make a `branch` so that you can
edit code without messing up the version that is currently working, and
when you've finished it, and you've tested it for bugs, and you're
(fairly) sure it won't break, then you can `merge` it back into the main
branch.

But what about when the code you want to change isn't on your local
machine? Then you need to `git clone` it from its remote repository. And
if it's your own repo (or the owner has given you the necessary
permissions), then that's all you need, you can `add`, `commit`,
`merge`, and `push` to your heart's content.

However, you might want to contribute code to a project owned by someone
you don't know at all. That's the joy of open source code, after all. In
that case, you need to *fork* their code. Which basically just means to
clone a copy of the repository to your own GitHub userspace. If their
code repo is at https://github.com/username/repository then you can fork
it by going to https://github.com/username/repository/fork. Or by
clicking on the 'Fork' button near the top of the repository GitHub
page. 

And then you clone your own repository, `add`/`commit`/`push` your
changes, and then make what GitHub calls a 'Pull Request', which sounds
opaque until you know that `git pull` combines two operations: first, a
`git fetch` which downloads new commits and branches from a remote
repository; and second a `git merge` of the changes in the remote branch
to your local branch.

So a 'Pull Request' is a request for the other GitHub repository to
`pull` the changes from your repository. And this is where GitHub
becomes a social network, because in the context of a 'Pull Request' the
owner of the repository can review your code and ask you to improve
specific bits before they agree to pull your changes.

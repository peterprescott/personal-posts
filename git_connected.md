---
title: "Git Connected"
date: '2021-03-05'
---

So you've installed Git and you've `add`ed and `commit`ted some files,
and even done some `branch`ing and `merge`-ing. But to really appreciate
the usefulness of Git, you need to sign up for
[GitHub](https://github.com/).

Or [GitLab](https://gitlab.com). Or maybe even Bitbucket.

I think of these web platforms as social networks for software
developers. Except that instead of sharing snapshots of your social
life, you share code that you've hacked together.

So go ahead and sign up for an account, verify your email address, and
now you're good to go! Suppose you want to backup those [hello world
scripts](2019_11_01), you can create a 'hello-world' repository with
your new GitHub username. Just go to
[https://github.com/new](https://github.com/new), type in the
'Repository name' you want (we can stick with `hello-world`), ignore all
the other options for now and 'Create repository'.

And now we can `git push` our code to GitHub, so that when fire and
flood assault our house and all our possessions are destroyed, our code
is still safe in the cloud somewhere. At least we hope.

Before we can push any code, we need to tell our local repository about
its new GitHub counterpart. By convention we call the Github counterpart
the 'origin', since it is generally treated as the primary
source-of-truth.

```
git remote add origin https://github.com/$USERNAME/hello-world
```

We're still not quite ready to `git push` -- if you do, you'll be told
that you must first "set the remote as upstream", like this:

```
git push --set-upstream origin master
```

And now we're done!

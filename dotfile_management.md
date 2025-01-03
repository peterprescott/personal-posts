---
title: "Dotfile Management"
date: '2022-01-07'
---

So in the last few posts we encountered two examples of 'dotfiles': 
`.zshrc` and `.vimrc` (although if like me your Vim is actually Neovim,
then your `.vimrc` may actually be found at `.config/nvim/init.vim`).
You will notice the two things the filenames have in common: the initial
dot (`.`) and the ending `rc`. The `rc` stands for something like 
'runtime configuration' (or perhaps just 'run commands'?), because of
course that is what these files do, they configure Zsh or Vim by being
read each time you run the program. And the dot (`.`) at the start of
the filename means that by conventional default they are not listed when
you `ls` the files in a directory.

Have a look for yourself:

```
cd ~    # change to your home directory
ls      # list the normal files
ls -a   # list **all** the files, including dotfiles
```

As you tweak your dotfiles to configure things to your taste, it becomes
increasingly important to backup your configuration. For which the
obvious solution is to [use Git](./everyone_needs_version_control).

Except the problem is that usually the files tracked by a Git repository
are all located within the same folder, whereas in order for your
dotfiles to be read by their respective programs, they need to be in the
expected location: the home folder for Zsh's `.zshrc` and Vim's
`.vimrc`, the `.config/nvim` folder for NeoVim's `init.vim`, and so on.

Fortunately, it turns out that this isn't a problem, as you can set up a
[bare](https://git-scm.com/docs/git-clone#Documentation/git-clone.txt---bare)
repository, which according to the documentation means that "instead of
creating directory and placing the administrative files in
directory/.git, [you] make the directory itself the $GIT_DIR". 

```
# first create your repo on Github, then:
git clone --bare https://github.com/$USERNAME/.dotfiles $HOME/.dotfiles 
```

When you are cloning a repository, "this obviously implies the
--no-checkout because there is nowhere to check out the working
tree"--but having cloned your `.dotfiles` repository, you can then set a
`dotfiles` alias which will run Git with your bare repository as the
`git-dir` and your home directory as the `work-tree`. You'll want to
save this alias in your `.zshrc`:

```
dotfiles='$(which git) --git-dir=$HOME/.dotfiles --work-tree=$HOME
```

Then, to make sure your status messages aren't overwhelmed with telling
you about all the other files in your home directory which you don't
want your dotfiles repository to track, you just need to configure it to
not show untracked files. 

```
dotfiles config --local status.showUntrackedFiles no
```

From there you can use the alias to `add`,
`commit`, `branch`, `checkout`, `push` and `pull` as you usually would
with any Git repository.

Credit for making this method known to the world belongs to
[StreakyCobra](https://news.ycombinator.com/item?id=11071754), and his
comment on HackerNews, although he was at pains to clarify that [he
didn't invent it](https://news.ycombinator.com/item?id=11072710). And if
this method doesn't appeal, the excellent [Archlinux
Wiki](https://wiki.archlinux.org/title/Dotfiles) includes a multitude of
other ways of managing your dotfiles.

My dotfiles repository is
[here](https://github.com/peterprescott/.dotfiles), feel free to have a
look!

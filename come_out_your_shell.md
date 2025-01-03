---
title: "Come Out Your Shell"
date: '2021-07-02'
---

This post isn't about learning how to be more extroverted so that you
can make friends and influence people. For that you can read Dale
Carnegie. The shell I am going to persuade you out from is the Bash
shell -- so that you can switch to the Zee shell.

Why might I want to do that?, you ask. And the answer, in a nutshell, is
autocompletion. And perhaps also customization.

First install it:

```
sudo apt install zsh
```

And then you can change the default shell to `zsh` like this:

```
chsh -s $(which zsh)
```

(See how we use the `which` command to specify the exact file location
of `zsh`, without paying any attention to what it actually is). Now when
you start a new terminal session, you should immediately begin with
`zsh`, instead of `bash`.

Raw `zsh` should already be an improvement, allowing you to press tab to
autocomplete the names of directories and such things. But you can do
add more magic by adding some lines to the `.zshrc` in your `$HOME`
directory.

First let's make sure we're using the modern completion system:

```
autoload -Uz compinit
compinit
zstyle ':completion:*' completer _expand _complete _correct _approximate
zstyle ':completion:*' use-compctl false
```

Then let's make the command-line prompt a little prettier:

```
export PROMPT='%B%K{blue} %2~ %k%K{white}%F{black}   %@ %f%k%b${NEWLINE} > '
export RPROMPT='%B$vcs_info_msg_0_%b'
NEWLINE=$'\n'
```

And then let's also add some details about the Git repository we're in
(if we're in one), and the branch we're on:

```
autoload -Uz vcs_info
precmd_vcs_info() { vcs_info }
precmd_functions+=( precmd_vcs_info )
setopt prompt_subst
zstyle ':vcs_info:git:*' formats '%F{yellow}*%b%f|%r'
```

And while we're at it, I'll confess that if it was me, I would always
use vim keybindings:

``` 
bindkey -v
```

Maybe we can talk about `vim` next time.

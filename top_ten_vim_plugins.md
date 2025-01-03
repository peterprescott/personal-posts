---
title: "Top Ten Vim Plugins"
date: '2021-11-05'
---

Having inducted you, in my previous post, into the mystical art of using
Vim, I will now share with you ten of the plugins that I find
useful. I won't give instructions about how to actually set them up,
beyond saying that if you follow the links then the repository READMEs
all have all the documentation you need for a quickstart.  I make no
claim to be by any means a Vim expert, and for each of them there may
well be superior alternatives (this becomes especially likely with the
passage of time), but these are all tools I have found helpful.

Now before installing any plugins, it might be helpful to have a plugin
manager: I use [vim-plug](https://github.com/junegunn/vim-plug).

1. The first plugin I think I ever installed was Tim Pope's
[vim-sensible](https://github.com/junegunn/vim-plug), because he says
"If you're new to Vim, you can install this as a starting point, rather
than copying some random vimrc you found", and I thought he probably
knew what he was talking about.

2. I tried a few different colour schemes, and
[gruvbox](https://github.com/morhetz/gruvbox) is easily my favourite.

3. As well as finding a colour scheme you like, you should make the
   status-line look pretty:
   [vim-airline](https://github.com/vim-airline/vim-airline) adds
   several useful titbits of data in satisfyingly stylish form. And you
   can pick a [theme]('vim-airline/vim-airline-themes') -- I like
   'minimalist'.

4. As you begin using Vim, and develop a personal configuration that
   suits your taste, you'll occasionally find that in order to have the
   necessary permissions to edit a file, you have to open it with
   `sudo`. And rather jarringly you suddenly have to operate without
   your carefully chosen colour-scheme and all your favourite plugins,
   and simply make do with the system defaults. Unless of course you
   have installed [suda.vim](https://github.com/lambdalisue/suda.vim),
   which allows you to edit a file with root privileges without running
   the whole session that way.

5. When you're using Vim to edit code, it can helpfully 'fold' away the
   body of a function or class. For Python, 
   [SimpylFold](https://github.com/tmhedberg/SimpylFold) makes sure the
   folding is syntactically correct.

6. It's also helpful to be able to comment out a line with the same
   command, regardless of whether the code you're editing is Python or
   Javascript or Vimscript or whatever. Tim Pope's
   [vim-commentary](https://github.com/tpope/vim-commentary) does this
   nicely.

7. For immediate linting and syntax checking,
   [ALE](https://github.com/dense-analysis/ale) is great.

8. Another helpful code editing tool is
   [tagbar](https://github.com/preservim/tagbar), which gives a list of
   all the variables, functions, and classes defined in your file.

9. With [NERDTree](https://github.com/preservim/nerdtree) you can then
   have a file system explorer in your Vim editor, giving you a
   fairly decent development environment.

10. Tagbar and NERDTree are great, but they both involve adding windows
   which can leave your screen space feeling a little squeezed. I use
   [winresizer](https://github.com/simeji/winresizer) to make resizing
   windows nice and easy.

11. As a final bonus, and very pleasing to the eye,
    [vim-css-color](https://github.com/ap/vim-css-color/tree/master)
    helpfully shows you what colour those impenetrable hex codes
    represent.

And if there are any vital vim plugins that I've missed, let me know!

---
title: "Windows in Windows (in Linux)" 
date: '2022-03-04' 
---

I still remember a t-shirt my Dad had when I was a kid, which said 'When
DOS closes, Windows open'. Actually, when I say I remember it, I have
only a vague recollection of it. Was the pun dependent on you reading
'DOS' like 'doors'? Was it 'Windows open', as if we're talking about
more than one 'window'? Or 'Windows opens', since Microsoft Windows is a
single thing?

Anyway, I have now long since stopped using Windows, and embraced the
joys and occasional irritations of using Linux. And this is not a post
about Linux's Windows emulator [`wine`](https://www.winehq.org/) (which
apparently stands for 'Wine Is Not an Emulator, so I guess I'm
describing it wrong), though that may well be a topic for another time.

No, this is just a little post about [`i3wm`](https://i3wm.org/) and
[`tmux`](https://github.com/tmux/tmux/wiki/Getting-Started), which give
you a keyboard-centric way of working with 'windows' inside (`tmux`) and
outside (`i3wm`) the terminal.

But let me describe for the sake of comparison my memory of Microsoft
Windows. When you open the computer you are greeted with a 'desktop', in
which there is some background image, and several program launch icons,
and a toolbar with a 'START' button that allows you to open other
programs not visible as icons on the desktop. When you opened a program
it appeared in its own 'window', a box that hovers over the background
desktop. You could 'maximize' it to fill the screen, or 'minimize' it to
disappear into its tab on the toolbar, or dragging the corners of the
window to resize it. Open another program and it would open in its own
window. Eventually you might learn a shortcut to get two windows to snap
into place beside each other, tightly filling the screen.

Snapping windows in place beside each other to tightly fill the screen
is what `i3wm` (the 'wm' stands for 'window manager'; the 'i3' bit has
[several
explanations](https://www.reddit.com/r/i3wm/comments/6tw2ut/why_is_it_called_i3/))
is all about. There is no desktop background. And there is no dragging
the corners of the window to resize it. A single window will fill the
screen. A second window will then split the screen 50:50 with the first.
A third? -- will split the screen in vertical thirds; or, if you then
instruct `i3` to split horizontally instead of vertically, it will split
the second half of the screen into quarters for the second and third
windows. And you can adjust the position of the window split with simple
configurable keyboard shortcuts.

Perhaps to appreciate how useful this is you need to be given an
absurdly large 32 inch monitor that would make neck ache as your turned
to look from one side of the screen to the other. Only when I switched
from a typical windows-on-desktop display to a tiling-windows display
was I able to begin appreciating the large monitor.

As well as 'windows', `i3` also lets you have and switch between
multiple different 'workspaces'. What is a 'workspace'? Well, suppose
instead of one absurdly large monitor, you had three normally sized
monitors. The display on each would be its own workspace. With three
monitors you could view three workspaces simultaneously. But with `i3`
you are not limited by the number of physical monitors you have. You can
have multiple workspaces on one monitor -- say one for your email, one
for reading [HackerNews](https://news.ycombinator.com/), one for editing
your code, and so on -- and switch back and forth between them with your
configured keyboard shortcuts.

And then there's `tmux`, which is in some ways similar to `i3`. Except
that instead of tiling the windows of whatever sort of fully-fledged
graphical applications on your GUI display (including perhaps a terminal
window for you to interact with the shell), `tmux` allows you to split
the window of your terminal into its own tiled 'panes', the size of
which you can adjust with configurage keyboard shortcuts. Tmux's 'panes'
are analagous to the 'windows' of `i3`, and tmux also has an equivalent
to the 'workspaces' of `i3`, which it calls (confusingly) 'windows'. 

Except perhaps it's not so confusing if you remember that `i3` and
`tmux` operate at different levels. The 'workspace' of `i3` takes up a
whole monitor; the 'window' of `tmux` takes up a terminal window.

If you're interested in understanding more about how to actually use
`i3` and `tmux` then you should read the documentation ([i3
here](https://i3wm.org/docs/userguide.html#_using_workspaces), [tmux
here](https://github.com/tmux/tmux/wiki/Getting-Started)).

I will note though that I wasn't a fan of the default key configuration
for either of them; but that's not a problem as it's easily
reconfigured. If you're interested you can see my setup in my dotfiles
([i3
here](https://github.com/peterprescott/.dotfiles/blob/master/.config/i3/config),
[tmux
here](https://github.com/peterprescott/.dotfiles/blob/master/.tmux.conf)).

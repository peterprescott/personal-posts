---
title: "Everybody Needs Version Control"
date: "2019-09-06"
tags: ['git', 'coding']
---

Most of my advice has no basis more reliable than my own meandering
experience. But there is one tip that I can offer you with 
absolute confidence: Use <strike>[sunscreen](https://www.youtube.com/watch?v=sTJ7AzBIJoI)</strike>
version control.

And when I say version control, I mean `git`.

If you're a software developer, then you will already know what I'm
talking about. But if you're not then you probably won't; and when I
begin trying to explain your eyes may well glaze over. 

Like that bit in the IT Crowd where Moss is explaining his code to Jen
and all she hears is white noise:

<iframe src="https://www.youtube.com/embed/_eUxpCG2n7o?rel=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

But if we translate the jargon of [software
*versions*](https://en.wikipedia.org/wiki/Software_versioning) into the
ordinary realm that most of us inhabit, what we are really talking about
is a way of managing changes in any text file. Forget the white noise of
computer code, and imagine instead that you are poet writing a sonnet
for your beloved: you open [your favourite text editor](https://missing.csail.mit.edu/2020/editors/), and you start your first draft:

``` text
You are like the shining sun,
With one look my heart you won.  
A single ray of beauty bright
like daylight dispersed my night...  
```

You save that first draft as `sonnet.txt`, but immediately you 
decide to try and improve it:

``` text
Shall I compare you to a summer day?
What a silly thing to try and say!
But my heart was wintry, dark and cold,
Until you came, like light, like Spring, like May...
```

Is that better? Is it worse? You're not sure, so you save it as
`sonnet-v2.txt`. You keep hacking away at it, attempting to turn your
heartfelt passion into eloquent poetry. At some point you finally
achieve the heights of this:

``` text
Shall I compare thee to a Summer's day?
Thou art more lovely and more temperate.
Rough winds do shake the darling buds of May,
And summer's lease hath all too short a date...
```

And you promptly fall asleep at your keyboard. You awake in the morning,
filled with a sense of exultant triumph, and delete all your files
except for the final `sonnet-v17.txt`, and open it up to print it out --
but then realize that this is the wrong version of your text. You must
have saved it in `sonnet-v15-edit-3.txt` or something...

The point I'm trying to make is that `git` isn't just for hackers, it's
also [for
poets](https://www.youtube.com/watch?v=BCQHnlnPusY&list=PLRqwX-V7Uu6ZF9C0YMKuns9sLDzK6zoiV&index=1).
It's for everyone who works with text files on computers. Except
admittedly it's a bit impenetrable. We'll come to that in our next post.

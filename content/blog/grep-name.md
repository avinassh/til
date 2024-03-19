+++
title = "Origin of grep name"
date = "2024-03-19T13:57:18+05:30"

tags = ["grep", "cmd", "vim", "vi"]
+++

Found this [Stackoverflow answer](https://stackoverflow.com/posts/1220118/revisions) which explains how the name grep came to be:

> It's interesting that the common Unix command grep was actually inspired by this ex command (and is named after the way in which it was documented). The ex command `:g/re/p` (grep) was the way they documented how to "globally" "print" lines containing a "regular expression" (re). When ed and ex were used, the `:p` command was one of the first that anyone learned and often the first one used when editing any file. It was how you printed the current contents (usually just one page full at a time using `:.,+25p` or some such).

(Note: the answer in itself is worth reading: **Your problem with Vim is that you don't grok vi**)
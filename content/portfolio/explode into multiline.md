+++
showonlyimage = true
draft = false
image = "/img/vim1/vim_macbook.jpg"
date = 2017-10-14T13:07:01+11:00
title = "Exploding lines into lines"
weight = 0
tags = [ "Development", "Go", "fast", "Blogging" ]
categories = [ "Development" ]
series = [ "Go Dev" ]
slug = "vimmer"
project_url = "https://github.com/gohugoio/hugo"
+++


This tutorial teach you how to paste a block of text into individual lines. Gif animation display at the end.


##### Suppose you have:

```
// Comment1
// Comment2
// Comment3
```
To be exploded into each line of below:
```
foo = 1;
bar = 2;
baz = 3;
```
As this form:
```
foo = 1; //Comment1
bar = 2; //Comment2
baz = 3; //Comment3
```

Vscode and Sublime can copy a block then use mutil-line editing shortcut to write to multiple lines.

Vim can do this task as well. Down side is I haven't figure out how to insert space and paste content as one go.

So, will be tedious if seperate 2 operation. But... I'm learning vim.

Vim has `i` for insert, `p` for paste, `a` for append.

##### The process is

    1. create visual block
        `ctrl + v` then `3j` or `down` triiger the creation of visual block.
    2. activate command (e.g. i, p, a, x)
        Hit p will paste in trail. shift+p paste at the front.
    3. write text, or copy
        Hit i won't work, use `shift + i` instead.
    4. esc to exit.

##### Examples

- batch insert after cursor (`shift + A`)

![visual_block+yank+paste](/img/vim1/multi-linee-shiftA.gif)

- batch insert before cursor (`shift + i`)

![visual_block+yank+paste](/img/vim1/insert-in-middle.gif)

![visual_block+yank+paste](/img/vim1/prepend-insert.gif)

- append (`p`)

![visual_block+yank+paste](/img/vim1/multiline-paste.gif)

- prepend (`shift + p`)

![visual_block+yank+paste](/img/vim1/prepend.gif)

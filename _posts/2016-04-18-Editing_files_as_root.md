---
layout: post
title: Editing files as root
tags: [tips and tricks,linux]
---

When editing a file as root one uses usually sudo, but doing it like this:

```Shell
sudo vi some_file
```

has a problem: When run as root, vi (or rather vim on linux) will not use the 
configuration for the root-account and that means you may lack syntax-highlighting
or your favourite plugin.

But there is a better way to do this....

First you need to to set up your environment by setting EDITOR, e.g. like this

```Shell
export EDITOR=vi
```

in your .bashrc (or whatever your shell uses).

Now you can edit a file via sudo simply like this:

```Shell
sudo -e some_file
```

and you get all the vi/vim configuration you probably have invested a lot of time in setting up.

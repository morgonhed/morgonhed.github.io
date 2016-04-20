---
layout: post
title: Start of week in gnome-shell calendar
tags: [tips and tricks, gnome-shell, debian, linux]
---

I am running gnome-shell on Debian and it annoyed me that the calendar would start the week on Sundays.

Here is how to change that:

First find you your locale:

```Shell
> echo $LANG
en_US.utf8
```

So I am using en_US. Now edit /usr/share/i18n/locales/en_US (change the last part to your locale) and search for
the setting for "first_weekday" and change it to this:

```Shell
first_weekday 2
```

Now regenerate your locale-files with

```Shell
sudo locale-gen
```

and finally restart the gnome-shell via "alt-F2" and "r". That's it - weeks now start on Mondays.


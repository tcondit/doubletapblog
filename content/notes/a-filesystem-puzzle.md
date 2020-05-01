---
title: "A Filesystem Puzzle"
date: 2020-04-30T13:04:14-07:00
draft: true
---

## A filesystem puzzle

What's going on here?

No `Make`, no problem.

```
❯ ls -l /usr/bin/M*
-rwxr-xr-x  1 root  wheel  18304 Sep 20  2019 /usr/bin/MergePef*
-rwxr-xr-x  1 root  wheel  18288 Sep 20  2019 /usr/bin/MvMac*
```

`Make` has entered the chat. Huh?

```
❯ ls -l /usr/bin/Make
-rwxr-xr-x  1 root  wheel  18288 Sep 20  2019 /usr/bin/Make*
```

`make` and `Make` are the same file. That's not unexpected, but why does it not
show up when doing a wildcard search?

```
❯ ls -il /usr/bin/Make /usr/bin/make
12885607604 -rwxr-xr-x  1 root  wheel  18288 Sep 20  2019 /usr/bin/Make*
12885607604 -rwxr-xr-x  1 root  wheel  18288 Sep 20  2019 /usr/bin/make*
```


---
title: "Git Version String"
date: 2020-04-28T11:57:51-07:00
draft: true
---

# A Git version string

I read about using the commit count and the short hash on some HN post, and had
to figure out how to do it economically. Could make a nice version number.
These are from a repo with 33 commits.

```shell
    ➜ echo $(git rev-list --count HEAD)-$(git rev-parse --short HEAD)
    33-f87d80f

    ➜ echo $(git rev-parse --short HEAD)-$(git rev-list --count HEAD)
    f87d80f-33
```

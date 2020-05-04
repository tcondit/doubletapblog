---
title: "Zsh Function for Exercism"
date: 2020-05-04T13:00:08-07:00
draft: true
---

### Zsh function ee

The exercises at exercism.io follow a common pattern, and it's tedious to keep
retyping the same command over and over again. Consistency + tedium is a good
problem to have, since it should be easy to fix. In this case, the fix is a
simple shell function.

```zsh
~/b/1_Projects/Exercism/python/matrix 6s
❯ func ee() { nvim -p README.md $(basename $(pwd).py) $(basename $(pwd)_test.py) }
```

Try it.

```zsh
~/b/1Projects/Exercism/python/matrix
❯ ee
```

Works.
{{< figure src="/zsh-function-ee.png" width="70%" >}}

<!-- {{< figure src="/zsh-function-ee.png" width="70%" title="Zsh function ee">}} -->
<!-- {{< figure src="/zsh-function-ee.png" title="Zsh function ee" >}} -->
<!-- <img src="/static/zsh-function-ee.png" alt="Zsh function ee" width="200"/> -->
<!-- ![ee](/zsh-function-ee.png "Zsh function ee") -->
<!-- {{< figure src="/media/spf13.jpg" title="Steve Francia" >}} -->


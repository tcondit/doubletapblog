---
title: "Python String Formatting"
date: 2020-05-01T12:17:27-07:00
draft: true
---

# Python string formatting cheatsheet

Notes from David Beazley's _Python Programming Language LiveLessons_
([1][1], [2][2]).

This is neat. The way he describes string formatting makes the evolution
clearer. I was looking for some examples like this recently, and was
disoriented by the syntax. With this progression, it makes more sense.

## Formatted output

#### Setup

```python
❯ python3
Python 3.7.7 (default, Mar 10 2020, 15:43:03)
[Clang 11.0.0 (clang-1100.0.33.17)] on darwin
Type "help", "copyright", "credits" or "license" for more information.

>>> name = 'IBM'
>>> shares = 100
>>> price = 32.2
```

#### Old style string formatting

```python
>>> # 10 spaces, right justified
>>> print("%10s %10d %10.2f" % (name, shares, price))
       IBM        100      32.20

>>> # 10 spaces, left justified
>>> print("%-10s %-10d %-10.2f" % (name, shares, price))
IBM        100        32.20
```

#### Newer style string formatting

```python
>>> # 10 spaces, right justified
>>> print("{:>10s} {:>10d} {:>10.2f}".format(name, shares, price))
       IBM        100      32.20

>>> # 10 spaces, left justified
>>> print("{:<10s} {:<10d} {:<10.2f}".format(name, shares, price))
IBM        100        32.20
```

#### f-strings: going a little further than the video

Ah, this is better. The output variables now come before the formatting
options.

```python
>>> # 10 spaces, right justified
>>> print(f"{name:>10} {shares:>10} {price:>10}")
       IBM        100       32.2

>>> # 10 spaces, left justified
>>> print(f"{name:<10} {shares:<10} {price:<10}")
IBM        100        32.2
```

For a decimals example, here's part of `mortgage2.py`. This was not readily
apparent at first. [This stackoverflow answer][3] reminded me that it's
derivative of what came before.

```python3
print(f"{month:>6d} {interest:>8.2f} {total_payment - interest:>8.2f} {principal:10.2f}")
```

And here's one showing how to format strings. This one got me at first because
I didn't think you'd need to wrap the whole string in single quotes and each
individual string in double quotes. (Hindsight: of course you do.)

Without it, this is output instead: `{Month:>5s} {Interest:>10s}
{Principal:>10s} {Remaining:>10s}`

```python3
print(f'{"Month":>5s} {"Interest":>10s} {"Principal":>10s} {"Remaining":>10s}')
```

## little file I/O on the side

I like this syntax for writing to a file.

```python3
out = open("schedule.txt", "w")
print(f'{"Month":>5s} {"Interest":>10s} {"Principal":>10s} {"Remaining":>10s}', file=out)
```

[1]: https://www.informit.com/store/python-programming-language-livelessons-9780134217321
[2]: https://learning.oreilly.com/videos/python-programming-language/9780134217314
[3]: https://stackoverflow.com/questions/45310254/fixed-digits-after-decimal-with-f-strings

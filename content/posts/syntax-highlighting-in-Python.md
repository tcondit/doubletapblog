+++
date = "2020-04-18T18:09:37-07:00"
draft = false
title = "Syntax Highlighting in Python"

+++

Let's see what this looks like
<br/>
<br/>

```python
DEBUG = False


class Luhn:
    def __init__(self, card_num):
        self.card_num = "".join(card_num.split(" "))

    def valid(self):
        card = self.card_num
        if not int(card.isnumeric()) or len(card) <= 1:
            return False

        # enumerate (used below) is a GREAT choice
        if len(card) % 2 == 0:  # even length string
            # return every other from front
            to_dbl = card[::2]
            sgl = card[::-2]
        else:
            # strip the last character, return every other from rear
            to_dbl = card[:-1][::-2]
            sgl = card[::2]
        if DEBUG:
            print(to_dbl, sgl)

        # maybe this should be a listcomp or genexp
        doubled = ""
        for c in to_dbl:
            c2 = int(c) * 2
            if c2 > 9:
                c2 -= 9
            doubled += str(c2)
        if DEBUG:
            print(doubled + sgl)

        sum = 0
        for c in doubled + sgl:
            sum += int(c)
        if DEBUG:
            print(sum)
        return sum % 10 == 0


if __name__ == "__main__":
    luhn = Luhn("0")
    # luhn = Luhn("0000 0")
    # luhn = Luhn("7")
    # luhn = Luhn("777 666   555")
    # luhn = Luhn('777 6t66   555')
    # luhn = Luhn('6~789   555')
    # luhn = Luhn('123456')
    # luhn = Luhn('1234567')
    print(luhn.valid())
```


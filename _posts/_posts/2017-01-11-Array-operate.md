---
layout: post
title: "Array operate"
date: 2017-01-11 22:12
categories: python


---

```python
a = [[1, 2, 3],
     [4, 5, 6],
     [7, 8, 9]]


def left_corner(a):
    new_array = []
    length = len(a)
    i = length-1
    while i >= 0:
        j = length - 1
        new = []
        while j >= 0:
            new.append(a[j][i])
            j = j-1
        new_array.append(new)
        i = i -1
    return new_array


def right_corner(a):
    new_array = []
    length = len(a)
    i = 0
    while i < length:
        j = 0
        new = []
        while j < length:
            new.append(a[j][i])
            j = j + 1
        new_array.append(new)
        i = i + 1
    return new_array


def left_rotate(a):
    new_array = []
    length = len(a)
    i = 0
    while i < length:
        j = length - 1
        new = []
        while j >= 0:
            new.append(a[j][i])
            j = j - 1
        new_array.append(new)
        i = i + 1
    return new_array


def right_rotate(a):
    new_array = []
    length = len(a)
    i = length - 1
    while i >= 0:
        j = 0
        new = []
        while j < length:
            new.append(a[j][i])
            j = j + 1
        new_array.append(new)
        i = i - 1
    return new_array

if __name__ == '__main__':

    print right_corner(a)
    print left_corner(a)
    print left_rotate(a)
    print right_rotate(a)

```


We will replace some part of the string or the whole string itself

We should specify:

1)
what we should replace?
what should be the replacment

2)
create search patterns.
Enclose the search patterns in parentheses to segregate them into capture groups


3) 
specify the replacment

4) 
Start the engine!

Replece those into xxx pix by  xxx pix

```txt
1280x720
1920x1080
1600x900
1280x1024
800x600
1024x768
```

By using () we can group symbols as a single entity.

() alse serve a function of creating a capture group
We create capture groups by closing pattern inside ().

When we create a capture group, each of them will assing a particular number to a capture group. Starting from \1. Next capture group will be \2.

Character outise capture groups, are used to find a pattern, but will not be saved into a capture group. Therefore in the example below 'x' is not captured.

Therefore the replacment format will be:
\1 pix by \2 pix

there are two patterns as a solution here:
- search pattern
- substitution pattern

in linux we use sed for substitution

```bash
sed  -r 's/([0-9]+)x([0-9]+)/1 pix by \2 pix/g' filename.txt
```

```js
/([0-9]+)x([0-9]+)/
/([0-9]{3,4})x([0-9]{3,4})/
/\1 pix by \2 pix/
```

## example 
format names

John Wallace -> Wallace,John

```js
/([a-zA-Z]+)\s([a-zA-Z]+)/
//
```


## curly braces repeater {m}

m number of repetitions of whatever proceeds this symbol

```txt
include:
834
519
645

exclude:
5
89
45643563456
25
```

We can simply scope digits by [0-9] character class.
We need anchor as we NOT matches done via subset of the string!
we could match 456 from 45643563456 without anchors

```js
/^[0-9][0-9][0-9]$/
/^[0-9]{3}$/
```


```txt
include:
aaab
aaaaaa

exclude:
a
aaaaaaa
```
if we want to catch a range of occurences with {m, n}
m is the minimum and n maximum number of repetitions

```js
/^[a-z]{4,9}$/
```


```txt
include:
hahahahaha
hahahahahahaha

exclude:
ha
baba
ba
haha
```

```js
/^(ha){4,}$/ // we can specify start range but not the end range. So at least 4 occurances and more

/^(ha){,4}$/ // we can specify max number of repetitions without a start
```


## plus repeater +

+ symbol is similar to *.
symbol+ reptresents one or more occurances of a character

```txt
include:
fooaaaabar
fooabar
fooaabar

exclude:
foobar
fooxxxbar
fooxbar
```

```js
/fooa+bar/
/fooa{1,}bar/
```

# question mark ? symbol

Question mark symbolises 0 or 1 occurences of a symbole before it

```txt
include:
https://website
http://website

exclude:
httpss://website
httpx://website
httpxx://website
```

```js
/https?:\/\/website/
```

# choice symbol | pipe (or)

```txt
include: 
logwood
plywood

exclude:
sapwood
rosewood
teakwood
redwood
```

```js
/(log|ply)wood/
```

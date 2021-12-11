
# General steps of building regex

1) What are the requirments
 What needs to be included?
 What needs to be excluded?

 2) Identify patterns in the inclusion list or the exclusion list
 Sometimes it is easier to use a regex for exclusion list and then negate that regex

 3) use pattern

 4) use regex engine (python, js, grep) to try out the pattern


# basic set and extended set of regular expressions

## basic set 

### wildcard asterisk * symbol
Catch one or more occurences of

We can catch text that starts with "foo" ends with "bar" and has 0 or more occurences of "a" in the middle

```js
/fooa*bar/
```

```txt
    foobar
    fooabar
    fooaaaabar
    fooxbar
```


### wildcard dot . symbol

strings we want to select:

```txt
foobar
fooxbar
foocbar
```

dont want to select:

```txt
baryfoo
foobar
fooxybar
```

we include ones that
- start with foo
- end width bar
- must have one letter in between


we can visualise it by separating pattern in 3 sections

foo | a | bar
foo | x | bar
foo | c | bar

we can represent one wildcard character by a dot

```js
/foo.bar/
```

### wildcard combo

innclusion:

foo || bar
foo | abc | bar
foo | bxc | bar
foo | z | bar

therefore we can catch "0 or more number of any character".

```js
/foo.*bar/
```

Reminder: Wildcard represents 0 or more occurences of specyfic character. Therefore:

```js
/foox*bar/
```

will catch words with 0 "x" characters in the middle, one, or more


### whitespace \s

\s is a singled whitespace

```txt
include:
foo bar
foo    bar
foobar

exclude:
fooxbar
```
We can catch 0 or more whitespaces with

```js
/foo\s*bar/
```

### character classes []

character class represents "one of the characters". It represents only one character position

```txt
include:
foo
coo
loo

exclude:
moo
doo
poo
boo
hoo
```


inclusion list:
  (f | c | l)   |   oo

  we can catch them by

```js
/[fcl]oo/
```

#### exponent operator inside character class, ^ symbol

sometimes it is better to use exclussiong list.
We can use [^abc]. This symbolises - any character, excluding "abc"

```txt
include:
foo
coo
doo
poo
loo

exclude:
moo
hoo
```
```js
/[^mh]oo/
```

#### ranges inside character classes

we can give a ascii range. For example [a-c]. "a" ascii value is 97 and "c" is 99/

```txt
include:
aee
bee
cee

exclude:
dee
gee
fee


outlier:
xee
```

we can catch this pattern by:

```js
/[a-c]ee/
```

assuming we want to catch chars in range but also 'x'

```js
/[a-cx]ee/
```
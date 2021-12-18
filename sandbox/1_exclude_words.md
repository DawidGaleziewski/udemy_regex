Kata
https://www.codewars.com/kata/614a4eaeeae33e003fde909b/train/javascript

exclude:
code
war

include:
codewars
barcode
warscode
anyothercombo

#! and other special chars are not threated as words and will split the string into two words!

```js
/^(?!^code$)(?!^war$)[a-z0-9]+/
```

Those are lookaheads:
(?!) - negative lookahead
(?=) - positive lookahead
(?<=) - positive lookbehind
(?<!) - negative lookbehind

(?>) - atomic group


Solution:

```js
const regex = /\b(?!(code|war)\b)\w+/gi;
"Codewars is a great place to find a great code war".match(regex)
```

leard:

## \b - word boundry
for getting standalone words in matches

## (?!) - negative lookahead to exclude cenrain matches

## g - match all in a string. Cuts a string into matches

## i - ignores case
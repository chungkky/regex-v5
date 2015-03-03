---
layout: page
title: Regular Expressions
subtitle: Reference
---
## [Topic Title One](01-one.html)

* Basic Regular Expressions
* Extended Regular Expressions
* Perl Compatable Regular Expressions
* Bash: grep & sed

## [Topic Title Two](02-two.html)

~~~
x.*
~~~
x followed by any character any number of times.

## Glossary

Where "x" means any alphabetic character
Where n or m means any numeric character
etc.

### Metacharacters
~~~
^x
~~~
"caret": Only looks at the beginning of the target string for x

~~~
x$
~~~
"dollar": Only looks at the end of the target string for x

~~~
x.y
~~~
"period": Looks for a string with any character in this position, _but_ there must be a character

~~~
x?y
~~~
"question mark": Looks for a string with any character in this position _or_ no character in this position

~~~
x*
~~~
"asterick": Looks for a string where the character x appears any number of times _or_ no times

~~~
x+
~~~
"plus": Looks for a string where the character x appears one or more times

~~~
[abc]
~~~
"square brackets": Looks for a string that contains any of the characters inside the square brackets ("expression") any number of times

~~~
[a-c]
~~~
"square brackets": Looks for a string that contains the first character a or any other character until the second character c based on dictionary ordering __Warning:__ Depending on your computer location settings what characters are included can differ!

~~~
[^abc]
~~~
"square brackets": Looks for a string that does _not_ contain any of the characters abc within the square brackets

~~~
x{n}
~~~
"curly braces": Looks for a string where the preceding character x appears exactly n times

~~~
x{x,m}
~~~
"curly braces": Looks for a string where the preceding character x appears at least n but not more than m times (n to m inclusive)

~~~
x{n,}
~~~
"curly braces": Looks for a string where the preceding character x appears at least n times (great than or equal to n)

~~~
(x)
~~~
"parantheses": Group parts of a search string together into a subexpression _or_ to make the result of the string inside the parantheses a variable which you can later refer back to __note__: Can be nested infinitely

~~~
x|y
~~~
"pipe": Looks for a string that matches the first character x and _if_ the first is not matched _then_ will look for a string that matches the second character

### Character and Positional Abbreviations

Note that these are implemented in most languages, but not absolutely all.  Search "Perl Compatable Regular Expressions" (PCRE) for more information.  There also might be more of these abbreviations in your chosen language.

~~~
\n
~~~
Represents a newline (line break)

~~~
\r
~~~
Represents a carriage return (return or enter)

~~~
\t
~~~
Represents a horizontal tab

~~~
\d
~~~
Represents any character in the range 0 - 9 (zero to nine inclusive)

~~~
\D
~~~
Represents any characters _not_ in the range 0 - 9 (zero to nine inclusive)

~~~
\s
~~~
Represents a whitespace character (space or tab)

~~~
\S
~~~
Represents any character that is _not_ a whitespace character (space or tab)

~~~
\w
~~~
Represents any character in the range 0 - 9, A - Z, a - z (all alphanumeric characters)

~~~
\W
~~~
Represents any character that is _not_ in the range 0 - 9, A - Z, a - z (all alphanumeric characters)

~~~
\bx
~~~
Represents the beginning of a word.  Looks for a string where the following character x appears at the beginning of a word

~~~
x\b
~~~
Represents the end of a word.  Looks for a string where the preceding character x appears at the end of a word

~~~
\Bx
~~~
Represents any position in a string that is _not_ the beginning or the end.  Looks for a string where the following character x does _not_ appear at the beginning of a word

~~~
x\B
~~~
Represents any position in a string that is _not_ the beginning or the end. Looks for a string where the preceding character x does _not_ appear at the end of a word
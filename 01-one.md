---
layout: page
title: Regular Expressions
subtitle: Introduction
minutes: 5-10
---
> ## Learning Objectives {.objectives}
>
> * Learn what regular expressions are and related terminology
> * Get comfortable reading regular expressions
> * Start building simple search strings

## Introduction
* Often shortened to regex or regexp (pronounced the way it looks)
* Regular expressions are written like algebra for words, using symbols in addition to "literal" characters
* Can look for letters, numbers, and characters, including whitespace
* Can set up logical operations like "if the first character in a word is a number, look to see if the last character in the word is a number"
* Used in web design for simple search engines and checking that inputs are formatted correctly
* Used in programming to find specific parts of a file to modify or use in a program

## Definitions
* A "string" is a set of characters, any characters
* The thing we're looking for, whether it's a phrase or word or set of numbers, is called the "target string"
* The thing you're searching, usually text files, is called the "source"
* And the regular expression we write is the "search string"
* A regex search string is correct if it finds __all__ of the examples of the target string in the source
* A regex search string is incorrect if it only finds some of the target strings or none of them or finds the wrong string
* A program uses the search string as definition to find the target string and do something to or with it


> ## Challenge Title {.challenge}
>
> Play around with the regex tester thing using your mouse to highlight the coloured areas of the search string and reading the definitions of the parts, try changing things

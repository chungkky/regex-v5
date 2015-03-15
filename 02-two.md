---
layout: page
title: Regular Expressions
subtitle: Finding stuff in citations
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Learn what regular expressions are and related terminology
> * Get comfortable reading regular expressions
> * Start building simple search strings


Please type or copy and paste the following into the top text area where it says "Write your regex here":
~~~
[A-Z]\w+
~~~

The file citations.txt is in the data/ directory.  Please copy and paste the content of that file into the bottom text area of Regexpal.  These citations are just a selection of open access papers written in a few different citation styles.  

> ## Challenge Title {.challenge}
>
> Would anyone like to try to guess what this search expression is finding in the text?

Let's start at the beginning.  A search string with just the following:

~~~
[A-Z]
~~~

Selects all capital letters.  It has analogous search strings in [a-z]  all lowercase letters and [0-9] all numbers.  Try replacing the A-Z with the previous two to see what gets selected.

The second part of the search phrase goes like this:

~~~
[A-Z]\w
~~~

The backslash and the w go together to make up what is called a "metacharacter".  It's a character that represents a character.  Metacharacters effectively make your search strings shorter by representing common search strings.  In this case, \w replaces the following:

~~~
([A-Z]|[a-z]|[0-9])
~~~

Which stands for "all capital letters OR all lowercase letters OR all numbers".  The vertical bars or lines or pipes indicate the "or".  The brackets are not strictly necessary, but if you try replacing the \w with the above string without the brackets the search string does not work the way you expect it to.  Like in math, you need to group certain parts of a function together to make sure the function is read correctly.  

Fortunately, we can use the \w metacharacter to avoid all this messiness.  

> NOTE: If you're having difficulty, you might be using the forward slash "/" instead of the backslash "\".  All metacharacters use the backslash, which is commonly found around the delete/backspace button on most keyboards.  

So let's get back to our original function:

~~~
[A-Z]\w+
~~~

The last plus sign is also a metacharacter.  It manipulates the previous metacharacter by saying to find whatever appears before it one or more times.  In this case, the search string is now looking for any string where \w, which is any alphanumeric character, appears any number of times.

If we were to read this search string out in normal language it would sound like it is searching for "A capital letter followed by one or more of any alphanumeric character".  In even simpler language, this search string finds every word that starts with a capital letter.  

If you look at what the search string found, you can tell that multiple capital letters like "DJ" are picked up, but just one letter standing alone like "L" does not get picked up.  If you really do want to find all words that start with capital letters, you probably don't want to get the author's initials.  This is all a part of how you build and refine search strings by looking at how you can identify aspects of what you're looking for that are distinctive and specific.

> ## Challenge {.challenge}
> 
> What is something you think would be a way to exclude initials from our search string?

So far we've seen how to pick out simple things like letters and numbers, how metacharacters can make that simpler, and how to read a search string.  There are a lot of other metacharacters to talk about, so in the next lesson we'll switch to a more realistic example.
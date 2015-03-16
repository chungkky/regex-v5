---
layout: page
title: Regular Expressions
subtitle: More complex expressions
minutes: 10
---

Last lesson we were just finding something generic, but we might as well try some more complicated strings related to citations.  We're going to look at some more common metacharacters and building them up.

Let's imagine I would now like to find all the articles that were published in PeerJ.  This is something most word processor search functions can handle, but the secret of all simple search engines is that they're using regular expressions behind the scenes. 

Type or copy the following string into the search text area:

~~~
PeerJ
~~~

As you can see, if you type in your search string, it is taken literally in regular expressions.  This is true for all alphanumeric characters.  

However, if you want to find a search string that contains a special character like an asterisk __*__ you need to be more careful because symbols have special meaning in regular expression-land.

Computers are super literal.  If you change your search string to 
~~~
Peerj
~~~

You won't get any results.  Capital letters and lowercase letters are different characters after all.  That is why using more general regular expressions with metacharacters like in the previous section might seem more complicated, but allows for a search that makes more intuitive sense.

> Note: Later we are going to discuss flags, which are modifications to the default behaviour of regex, and one of those is making an expression case insensitive.

## Metacharacters
One of handyest metacharacters is the period.  A period indicates that there should be a character in the place where the period is, but it doesn't matter what character it is.  

~~~
Peer.
~~~

If you were to change one of the "PeerJ"s in the text area to "PeerK" or even "Peerj" it would still be picked up by this search string.  This would __not__, however, pick up just "Peer" because the period says there must be an alphanumeric character there.  If there might be no character you can use a question mark instead.

~~~
Peer?
~~~

Right now we're literally just picking up the word we're searching for.  What we really want is all of the citations that are published in PeerJ, not just the word PeerJ.  This is where the asterisk comes in.

Try putting an asterisk after the period.

~~~
Peer.*
~~~

What do you find?  All the text after the word Peer is selected.  Why?  Because the period-asterisk combo can be translated to "an alphanumeric character any number of times".  

> ## Challenge {.challenge}
>So since we know the name of the journal is usually in the middle of a citation and not at the beginning or end, how would you modify this search string to highlight the whole citation?

Metacharacters _usually_ are influenced by the character immediately in front of them, as we saw with the "\w+" in the previous section. So this search string:

~~~
Peer*.
~~~

Is not the same as the previous search string.  The asterisk is now acting on the "r", saying "the character r can appear any number of times, then some letter comes after".  Just like how there are the rules of operation in algebra (BEDMAS/PEDMAS), the order in which you write the search string matters.  

So now we have in our search arsenal 

~~~
( ) [A-Z] [a-z] [0-9] | . * ? + \w
~~~


## find all citations from before 2010: 
reversing/making a NOT statement

## find all citations with the last name author 
you know their last name, but not their first, or initial, or even how it's written
whitespace metacharacter
\w and \W

I do need to warn periodically that the use of metacharacters can vary slightly depending on the language you're using.  Especially the "shortcut" metacharacters like \w.  This is OK because \w is just equal to a-z 0-9.

but there could be comma whitespace, just whitespace, etc
and we want to get the whole citation
~~~
(Dixon\W*\w).*
~~~

If we knew that the first author's last name is always at the beginning of the citation we can use caret

If we know the DOI is always the last string in the citation we can use dollarsign

## Some DOIs have slashes in them

Escaping characters :(
Most of the time, the reason why long regular expressions look terrifying is because of having to escape characters



## Flags
The __g__ in this string is a flag and not part of the search string.  Instead it is modifying how the regular expression searches the source.  On the top right of the window is a menu called "Flags"  and you can click on it and see the three most common flags people use.  If you un-click the g flag the search string will only find the first example in the source that matches the search string.

If you select the __i__ flag then the regular expression you wrote will include results that match both the uppercase and lowercase version.  Sometimes this will save you time in writing the expression to account for both, but in more complicated search strings letter case may be significant.

The __m__ flag is also a bit dangerous.  In short, when the program reads through the source usually it looks word by word.  With __m__ activated the program reads in units of lines.  Therefore if you use a caret to signal the beginning or a dollar sign to signal the end normally it searches for the beginning and the end of the word, but with __m__ it searches the beginning and the end of lines.

> ## Challenge {.challenge}
> 
> Try finding all the citations where the first author's name starts with the letter B.


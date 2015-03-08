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

The file citations.txt is in the data/ directory.  You can copy and paste the content of that file into the "text" area of the Regexr.  These citations are just a selection of open access papers that have DOIs (digital object identifier) which act like semi-permanent URLs and are written in a few different citation styles.  

The default search string in the "Expression" bar is:
~~~
/([A-Z])\w+/g
~~~


> ## Challenge Title {.challenge}
>
> Would anyone like to try to explain what this search expression is finding in the text?


Let's take it apart and just delete everything between the forward slashes except for the following:
~~~
//g
~~~

>__Note:__ Despite the common confusion the forward slash leans to the right and the backslash leans to the left.  We'll be using both.  Forwardslash is usually in the bottom row of keys next to Shift and backslash is usually up around Backspace on Anglo keyboards.

The reason why you can't delete the two slashes is because they signal the beginning and the end of the search string.  Depending on what programming language you use this might be different, but one thing that tends to be consistent is the presence of flags.  We will get into the most common flags later.

I would now like to find all the articles that were published in PeerJ.  This is something most search functions can handle, but let's replicate it with the regular expressions the search engine is using. 

~~~
/PeerJ/g
~~~

As you can see, if you type in your search string, it is taken literally.  This is true for all alphanumeric characters.  

However, if you want to find a search string that contains a special character like an asterisk __*__ you need to be more careful because symbols have special meaning in regular expression-land.

Computers are super literal.  If you change your search string to 
~~~
/Peerj/g
~~~

You won't get any results.  Capital letters and lowercase letters are different characters after all.

## Metacharacters
One of handyest metacharacters is the period.  A period indicates that there should be a character in the place where the period is, but it doesn't matter what character it is.

~~~
/Peer./g
~~~

If you were to change one of the "PeerJ"s in the text area to "PeerK" or even "Peerj" it would still be picked up by this search string.

But right now we're literally just picking up the word we're searching for.  What we really want is all of the citations that are published in PeerJ, not just the word PeerJ.  This is where the asterisk comes in.

Try putting an asterisk after the period.

~~~
/Peer.*/g
~~~

What do you find?  All the text after the word Peer is selected.  Why?  Because the period-asterisk combo can be translated to "a character any number of times".  

> ## Challenge {.challenge}
>So since we know the name of the journal is usually in the middle of a citation and not at the beginning or end, how would you modify this search string to highlight the whole citation?

Metacharacters _usually_ are influenced by the character immediately in front of them, so this

~~~
/Peer*./g
~~~

Is not the same as the previous search string.  The asterisk is now acting on the "r", saying "the character r can appear any number of times, then some letter comes after".  Just like how there are the rules of operation in algebra (BEDMAS/PEDMAS), the order in which you write the search string matters.  And just like with algebra, you'll just have to remember them, and there's no great mnemotic to help you out.

You may remember that the period signals that there _must_ be a character in that position, but what if you aren't sure there is?  Somehow, sensibly, the metacharacter you use here is a question mark.

And if a character appears one or more times it's a plus sign.

## find all citations from before 2010: 
reversing/making a NOT statement

## find all citations with the last name author 
you know their last name, but not their first, or initial, or even how it's written
whitespace metacharacter
\w and \W

I do need to warn periodically that the use of metacharacters can vary slightly depending on the language you're using.  Especially teh "shortcut" metacharacters like \w.  This is OK because \w is just equal to a-z 0-9.

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


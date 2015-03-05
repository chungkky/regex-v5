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

What do you find?  All the text after the word Peer is selected.

> ## Challenge {.challenge}
>So since we know the name of the journal is usually in the middle of a citation and not at the beginning or end, how would you modify this search string to highlight the whole citation?

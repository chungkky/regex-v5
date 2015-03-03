---
layout: page
title: Regular Expressions
subtitle: Finding DOIs
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Learn what regular expressions are and related terminology
> * Get comfortable reading regular expressions
> * Start building simple search strings

The file citations.txt is in the data/ directory.  You can copy and paste the content of that file into the text area of the Regexr.

These citations are just a selection of popular papers from PLOSOne.  They all have DOI numbers and we would like to pull out all those DOIs.  Now, if you just try to use the "find" function you can grab the word "doi", but what about the string after it?  We really don't want to go in and copy-paste them all individually.

~~~
doi.*
~~~
doi followed by any character any number of times.

* Also catches "doing"
* Doesn't catch capital letters DOI

* Flag "ignore case" in bash or javascript or some others is /i or /I
* To find all cases of a match and not just the first, need flag /g or /G

~~~
doi.*/gi
~~~

* We don't want just any word that starts with doi, we need to specify somehow
* Our DOIs are all written doi:xxxx so let's put that colon in there

~~~
doi:.*/gi
~~~



> ## Challenge Title {.challenge}
>
> Description of a single challenge.
> There may be several challenges.

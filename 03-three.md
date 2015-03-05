---
layout: page
title: Regular Expressions
subtitle: More complex expressions
minutes: 10
---

## Flags
The __g__ in this string is a flag and not part of the search string.  Instead it is modifying how the regular expression searches the source.  On the top right of the window is a menu called "Flags"  and you can click on it and see the three most common flags people use.  If you un-click the g flag the search string will only find the first example in the source that matches the search string.

If you select the __i__ flag then the regular expression you wrote will include results that match both the uppercase and lowercase version.  Sometimes this will save you time in writing the expression to account for both, but in more complicated search strings letter case may be significant.

The __m__ flag is also a bit dangerous.  In short, when the program reads through the source usually it looks word by word.  With __m__ activated the program reads in units of lines.  Therefore if you use a caret to signal the beginning or a dollar sign to signal the end normally it searches for the beginning and the end of the word, but with __m__ it searches the beginning and the end of lines.

> ## Challenge {.challenge}
> 
> Try finding all the citations where the first author's name starts with the letter B.


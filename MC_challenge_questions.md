# Multiple Choice Challenge Questions for Regular Expressions in Python

> ## Finding lines of matching text {.challenge}
>
> ~~~
> Caenorhabditis elegans
> Caenorhabditis briggsae
> Caenorhabditis remanei
> Caenorhabditis remanei
> Caenorhabditis elegans
> Caenorhabditis remanei
> Caenorhabditis elegans
> ~~~
>
> From the above list of nematode species name and we want to extract only 
> those from the species `Caenorhabditis elegans`
>
> Which command below would allow us to do so?

> a. 
>~~~
> for nematodes in readings:
>	if re.search(nematodes, 'Caenorhabditis elegans')
>		print r
>~~~
>
 > b. 
> ~~~	
> for nematodes in readings:
>	if re.search('Caenorhabditis elegans', nematodes)
>		print r
>~~~
>
> c. 
>~~~
> for nematodes in readings:
>	if re.search(nematodes, 'elegans')
>		print r
>~~~
>
 > d. 
> ~~~
> for nematodes in readings:
>	if re.search('elegans', nematodes)
>		print r
>~~~
>
> e. Both b & d

> ## Extracting matching text from a string {.challenge}

> Where `pattern` is a variable containing a string, and typing:
>
> ~~~
> match = re.search(pattern, 'Baker 1\t2009-11-17\t1223.0')
> print match.group(1) 
> ~~~ 
>
> returns:
 >~~~
> 17
>~~~
>
> What string in pattern would result in the above output?
>
 > a. `'....-(..)-..'`
>
 > b. `'..  -..-(..)'  `
>
> c. `'....-(..)-(..)'`
>
 > d. `'(....-..-..)'`
>



 

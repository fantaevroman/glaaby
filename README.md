# magic
Magic is a free console tool to make tedious tasks at production fast and safe


#How to use:

1. run magic interactive mode:
> *magic*

2. write script you want to magic to perform, use TAB! For auto completion!
Remember magic's power is autocompletion you'll spend a feww seconds for this script.
You don't need to memorize it.

{action:read filenames, location: /tmp} =>
{action:file to lines} =>
{action:replace in line, 
pattern:{start} {word:count} {word:index} {end}, replace: index:${set:"new value"}} =>
{action:write, location:user@mysshserver:/tmp/} =>
{action:run script}

3. Magic output:

#How to install




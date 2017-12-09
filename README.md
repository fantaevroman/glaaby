# magic
Magic is a free console tool to make tedious tasks at production fast and safe


#How to use:

1. run magic interactive mode:
> *magic*

2. write script you want to magic to perform, use TAB! For auto completion!
Remember magic's power is autocompletion you'll spend a feww seconds for this script.
You don't need to memorize it.
```
{action:go to, location: /tmp} =>
{action:read filenames} =>
{action:file to lines, filename:name} (file, line)=>
{action:replace in line, 
pattern:{start} {word:count} {word:index} {end}, replace: index:${set:new value}} =>
{action:write to file, location:user@mysshserver:/tmp/my.txt} =>
{action:run script}
```
3. Magic output:

4. You have many machines at production, forget to log there 
every time you need to run script, use magic! You have auto completeon
for dirrectories on remote mashines too.

```
{action:go to, location:root@dev-env-server} =>
{action:go to, location:root@deeper-inside-server:/tmp} =>
{action:read filenames} name =>
{for server: [root@server1:/tmp, root@server2:/tmp, root@server3:/tmp]}
  {action:copy, location:server} 
{end for} =>
{action:run script}
```

5. Use your own language to extend the script, here kotlin examle.
```
{action:http request, url:magic.com} (responce, body)=>
{action:kotlin, 
source:"
fun parce(body:String){
println(body)
}"} =>
{action:write to file, location:localhost:/tmp} =>
{action:run script}
```

6. Performance 
Magic written in kotlin so you should expect the best speed. 
You can run tasks in parallel! Finally you can use all your CPU cores at your scripts :)

#How to install




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
body => {
println("your brand new text at the page top" + body)
}"} =>
{action:write to file, location:localhost:/tmp} =>
{action:run script}
```

6. Transfer data between Databases. Tunnel your path if you need to.
Once you have an tunnel you can go there at any line of code.
```
{action:tunnel, location:user@server1} =>
{action:tunnel, location:user2@server2} =>
{action:go to, location:user@server2} =>
{action:mysql select, sql: select * from users} records =>
{action:kotlin, source:"
records:Iterator<Record> =>{
let mongoDbDocuments:List<Document> docs = ArrayList()
//..translate sql record to mongoDb and return
//use debugger and IDE power to make things fast
}
"} =>
{action:mongo insert, location:mongoserver:/mydatabase}
{action:run script}
```
7. Map reduce...

8. Parallel executions...

7. Performance
Magic written in kotlin so you should expect the best speed. 
You can run tasks in parallel! Finally you can use all your CPU cores at your scripts :)


8 Compilation
Before you can execute script it will be compiled, so less problems with typos.

#How to install

# magic
Magic is a free console tool to make tedious tasks at production fast and safe


#How to use:

1. run magic interactive mode:
> *magic*

2. write script you want to magic to perform, use TAB! For auto completion!
Remember magic's power is autocompletion you'll spend a feww seconds for this script.
You don't need to memorize it.
```
goTo(location:"/tmp") =>
readFileNames() =>
map(fileName -> readTextFile(fileName)) =>
replaceInLine(pattern: "{start} {word:count} {word:index} {end}", 
replace: "index:${set:new value}"}) =>
writeToFile(location:"user@mysshserver:/tmp/my.txt") =>
run()
```
3. Magic output:

4. You have many machines at production, forget to log there 
every time you need to run script, use magic! You have auto completeon
for dirrectories on remote mashines too.

```
tunnel(location:"root@dev-env-server") =>
tunnel(location:"root@deeper-inside-server:/tmp") =>
goThere()=>
readFilenames() => (name) ->{
for server: ["root@server1:/tmp/", "root@server2:/tmp/", "root@server3:/tmp/"]{
  copyFile(location:server + "copied_file" + name) 
}} =>
run()
```

5. Use your own language to extend the script, here is kotlin examle.
```
httpRequest(url:magic.com} => 
kotlin(
(response, body) -> {
return "your brand new text at the page top" + body
}) =>
writeToFile(location:"localhost:/tmp") =>
run()
```

6. Transfer data between Databases. Tunnel your path if you need to.
Once you have an tunnel you can go there at any line of code.
```
tunnel(location:"user@server1") =>
tunnel(location:"user2@server2") =>
goThere()=>
mysqlSelect(sql: "select * from users") => kotlin (record ->{
//..translate sql record to mongoDb Document and return
//use debugger and IDE power to make things fast
}) =>
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

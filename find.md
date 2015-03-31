
###title: "find with xargs"
###date: 2015-03-31 10:11




- find $mypath -name *.gz -mtime +10 -print0 | xargs -0 -r rm -f


- Prompt User Before Execution using -p option

```
Using option -p, you can confirm the execution of the xargs command from the user.

Considering the previous example, if we want to confirm each execution of the /bin/echo command by the user, use the -p option along with -n option as shown below.

$ echo a b c d e f| xargs -p -n 3
/bin/echo a b c ?...y
/bin/echo d e f ?...a b c
y
d e f
In the following output, I said “n” to all the echo output. So, xargs did not execute anything.

$ echo a b c d e f| xargs -p -n 3
/bin/echo a b c ?...n
/bin/echo d e f ?...n
/bin/echo ?...n
``` 

```
$ echo a b c d e f| xargs -n 3
a b c
d e f
```

$ find . -name "*.c" | xargs rm -rf

$ ls

one.h  two.h  The Geek Stuff.c


- find . -name "*.c" -print0 | xargs -0 rm -rf

```
In this situation, use the -print0 option with find command and -0 option with xargs command to delete files including those that has space in the filenames as shown below.
```
- find . -name '*.c' | xargs grep 'stdlib.h'


- ls | xargs -I {} mv {} 20080815-{}

```
This works because {} is a placeholder meaning "the current argument". (You can use xxx or yyy or any other string instead of {} if you want, as well, and it'll do exactly the same thing.) -I implies -n1, because you want to act on each file individually.
Or you might want to move all the files in directory 1 into directory 2:
```

- ls dir1 | xargs -I {} -t mv dir1/{} dir1/{}
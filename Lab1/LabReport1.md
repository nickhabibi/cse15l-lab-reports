## Lab Report 1

In this Lab report, we are going to discuss the filesystem commands `cd`, `ls`, and `cat` and show examples of using each command.

## cd

- Using `cd` with no argumennts

```
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ 
```

The working directory changes to the `home` or `~` directory. since no directory is specified, CWD changes to `home` by default. 
No errors.

- Using `cd` with a path to a directory as an argument

```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```

The working directory changes to the specified directory.
No errors.

- Using `cd` with a path to a file as an argument

```
[user@sahara ~/lecture1]$ cd Hello.java
bash: cd: Hello.java: Not a directory
[user@sahara ~/lecture1]$ 
```

We get the error `bash: cd: Hello.java: Not a directory` because the current working directory can only be changed to another directory and Hello.java is a file.

## ls

- Using `ls` with no arguments

```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
[user@sahara ~/lecture1]$ 
```

The files and directories inside the current working directory are listed.
No errors.

- Using `ls` with a path to a directory as an argument

```
[user@sahara ~/lecture1]$ ls messages/
en-us.txt  es-mx.txt  it.txt  zh-cn.txt
[user@sahara ~/lecture1]$ 
```

The files and directories inside the specified directory are listed.
No errors.

- Using `ls` with a path to a file as an argument

```
[user@sahara ~/lecture1/messages]$ ls en-us.txt
en-us.txt
[user@sahara ~/lecture1/messages]$ 
```

The specified file is listed. 
No errors.

## cat

- Using `cat` with no arguments

```
[user@sahara ~]$ cat
hello
hello
```

If no file is specified, cat reads from standard input and then displays it.
No errors.

- Using `cat` with a path to a directory as an argument

```
[user@sahara ~]$ cat lecture1/
cat: lecture1/: Is a directory
[user@sahara ~]$ 
```

We get the error `cat: lecture1/: Is a directory` because a directory cannot have raw content to be read.

- Using `cat` with a path to a file as an argument.

```
[user@sahara ~/lecture1/messages]$ cat it.txt
Ciao mondo!
[user@sahara ~/lecture1/messages]$
```

The contents of the file `it.txt` are read and then written to standard output.
No errors.





   


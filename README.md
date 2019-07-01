# BASH COMMANDS

Bash is the popular shell for UNIX-like systems.

## echo
The echo command prints the text

```
echo hello world
-> hello world
 // Use `>` character to write it to a file. It over writes the file.
 echo hello world > a.txt

 // Use `>>` double greater then to append to a file.
 echo hello again >> a.txt
```

## echo $SHELL
Check which shell currently using
Example: 
```
echo $SHELL
```
  * `echo` is a command
  * `$SHELL` is the example of a argument.

## ls
Lists files from current directory.
Example:
Lists all the files in the current directory.

Lists files from `/` root directory.
```
ls
ls /
```

## pwd
It displays the current directory you are in. It stand for print working directory.

```
pwd
```

## cd
You can change the directory you are in using cd. `cd` stands for change directory.

```
cd Desktop
```

## man (manual)
You can learn about any bash command you want to know about using this command. Type the command name after the `man` you 
wan to know about.

```
man --command name--
man ls
```

## Special Directory
These are some of the special directories:
1. `..` - the parent directory (use it to navigate to parent)
2. `.` - the current directory
3. `~` - you root directory (it will navigate to root directory)

## cat
Used to concatenate all the files from the argument. You can also use it to display the content of a single file.

Example: 
```
cat a.txt b.txt
```


## cp (copy command)
Copy a file to another directory or file name. You can also copy a file to make a duplicate of the file.

Example:
```
cp --source-- --target--
cp a.txt b.txt

//Copy multiple file into a directory.
cp a.txt b.txt source/

```
If you have a directory full of files and directories that you want to copy to a new place. You can use the flag `-r` to 
recursively copy

```
cp -r day-1 new-day-1
```


## mv (move command)
The `mv` command is used to  rename or overwrite files and directories.
You can also use it to rename the file to do that:
Set the first argument to the original file name and the second argument to the new file name.

```
// Rename
mv old.txt new.txt
// Override (it will override one file to another)
mv old.txt oldexists.txt
```

Example:
```
cp --source-- --target--
cp a.txt b.txt

//Copy multiple file into a directory.
cp a.txt b.txt source/
```

## mkdir
Creates a new directory to the current directory.

Example
```
mkdir react

// -p create the dir if it doesnot exists
mkdir -p react/redux
```

## brace expansion sequences
It can be tedious to type out numerical list by hand so you can use brace expansion.

```
echo hello{1..5}
// hello1 hello2 hello3 hello4 hello5

echo hello{1, 2}.txt
// hello1.txt hello2.txt

echo img{0..40..10}
// prints after every 10 img0 img10 img20 img30 img40
```

## echo
It prints out the command.

Example:
```
echo Hello World
// Hello World

echo hello{_,}.txt
// hello_.txt hello.txt
```

## rm (remove file)
Used to remove file

```
rm b.txt

// remove multiple files
rm a.txt b.txt c.txt

// Remove entire directory -r stands for recursively
rm -r --dirname--
```

## wc
It prints number of lines, number of words and and bites in a file. To see independent info you can pass flags.

```
// it will let you type lines and once you press ctr + d you stop.
wc

// we a.txt

// -l number of lies
wc -l

// number of bites
wc -c

// number of words
wc -w

```

## Head
Head prints the first part of the file.

```
head main.txt
// For specifying the number of lines
head main.txt --lines=5
head -n5 main.txt
```

## tail
Reads form the last of the file.

```
tail main.txt --lines=5
tail -n5 main.txt
```

## Absolute and Relative Path
Paths that starts with `.` or `..` is called relative paths.
Paths that starts with `/` is called absolute paths.

## > && >> && <

1. `>` is used to write to a file.
2. `>>` is used to append to a file.
3. `<` use it to read a file into the input of the program
```
echo line one > a.txt
// Append to a file
echo line two >> a.txt

// < for the input
wc -c < a.txt
```

## pipe `|`

The pipe character feed the output of one program to the input of another program.

It will take the output from the `ls -1` and feed it to the `wc` command which will give the number of lines.
```
ls -1 | wc -l
```

Complex Example:
```
// Fetch the file and prints out the content.
curl https://www.gutenberg.org/cache/epub/2701/pg2701.txt

// The output of above will be sent to gunzip for uncompressing the content.
curl https://www.gutenberg.org/cache/epub/2701/pg2701.txt | gunzip

// It will search for the word you want.
curl https://www.gutenberg.org/cache/epub/2701/pg2701.txt | gunzip | grep -i whale

// Will give us the number of lines
curl https://www.gutenberg.org/cache/epub/2701/pg2701.txt | gunzip | grep -i whale | wc -l

```

## grep
You can search for pattern or words in file.
Use `-i` Ignores, case for matching.

```
ls -1 | grep desktop

```

## cal (calender)
Shows the calender
```
cal
cal 2018
cal oct 2018
cal -3
```

## date
Date command shows the date.

```
date
```

## fold
Fold command helps you change the way the data is displayed.
`-w` width
`s` It will not break words in between
```
curl https://www.gutenberg.org/cache/epub/2701/pg2701.txt | gunzip | head -n20 | fold -sw 30
```

## curl
Little handy tool for making a HTTP request.

```
curl --url--
```

## `` backticks
You can use backticks for the purpose of joining a variable and constant.

```
echo Greeting from the year `date +%Y`
```

## arithmetic `$((...))`
With this command you can use it for a arithmetic.

```
echo 2 + 2 = $((2 + 2))
```

## $PATH
This is a special environment variable called `$PATH`. It contains list of places separated by `:` where bash will look to 
find when you type a command.


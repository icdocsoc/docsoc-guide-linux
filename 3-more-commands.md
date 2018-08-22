# More commands

```
Brief (to be removed)

touch
cat
mkdir
rm (-rf)
cp (-R)
mv
sudo (+ which directories you need to sudo to write to)
ssh (and how to ssh into labs)
grep (-n) (alternatives: ag)
chmod and permission numbers
man [...]
```

You've already learnt about `ls` and `cd`. Now, we'll teach you some more useful (nay, essential) Linux commands.

Don't worry if the following list of commands seems very long at first. After lots of experience with using the Linux terminal you'll gradually start to memorise how each one works.

Remember, whenever a command needs a file/directory path you can give it as either an absolute path or relative to your working directory.

## `touch`

This is a really easy command. `touch <file>` simply creates an empty file at the specificed location! Here it is demonstrated:

![touch](assets/commands/touch.png "touch")

```
Note that files don't have to end with an extension like `.txt`. They can be called whatever you want! Files only have extensions so that programs know what to do with that type of file.
```

## `cat`

`cat <file>` prints the contents of that file to your screen. In the following example we've already created a file called `hello.txt` in our home folder, which contains the text `hello world`.

![cat](assets/commands/cat.png "cat")

```
Whenever something is printed to the screen it belongs to what is called a 'stream'. There are two output streams, called stdout and stderr, and one input stream called stdin. This is quite an advanced topic but for more information, see the Streams section.
```

## `mkdir`

`mkdir <directory>` creates an empty directory at the specified path.

![mkdir](assets/commands/mkdir.png "mkdir")

## `rm`

`rm <file>` removes that file **permanently** from your computer. Terminal commands don't use the Recycle Bin! Be very careful when using `rm` to remove files. In the example below  we use `touch` to create an empty file and `rm` to remove it.

![rm](assets/commands/rm.png "rm")

There's one catch: if you try to use `rm` on a directory, an error is printed! To remove a directory (**and everything inside it**) we must add the `-r` and `-f` flags.

* `-r` tells the computer to remove the directory recursively (i.e. to remove all subdirectories, subsubdirectories, etc.)
* `-f` tells the computer to erase all files/directories without asking for confirmation, no matter what the file permissions are

We can stick these flags together into one string, so typing `rm -rf <directory>` will remove that directory from the computer. **Remember this is a permanent action.**

![rm -rf](assets/commands/rm-rf.png "rm -rf")

## `cp`

## `mv`

## `sudo`

## `ssh`

## `grep`

## `chmod`

## `man`

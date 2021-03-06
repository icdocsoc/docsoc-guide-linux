# The command line

```
Brief (to be removed)

Open terminal
Ctrl+ and ctrl- to zoom in and out
Type ls
Teach ls (-a, -l)
Teach cd
TIP: THE UP AND DOWN BUTTONS CAN BE USED TO SELECT PREVIOUS COMMANDS
File directory structure (/ and ~ meaning)
Understanding file permissions
. means current directory
.. means parent directory
Relative vs absolute paths
Hidden files (start with .)
```
## Using the terminal

In your applications folder there's a program called 'Terminal'. The Linux terminal provides a **command line interface** between you and your computer, which is named as such since the only thing you're allowed to do is enter commands on-screen. The terminal comes with a huge list of preset commands, and you can install even more commands with **package managers** (see the Package Managers section). Almost all programming on Linux involves good knowledge of how to use the command line interface.

For now, we'll focus on some basic commands that allow you to interact with your computer. Start by opening the Terminal app; you will be greeted with a command line interface like so:

![startup](assets/commands/startup.png "startup")
###### Don’t worry about the left hand side too much yet - this reads as your username ‘@’ the hostname of your computer

```
TIP: You can use Ctrl+ and Ctrl- to make the text bigger and smaller.
```

Before we begin, we'll have to explain some terms. Don't worry if these don't make sense at first, you'll pick up concepts quickly when experimenting with the `ls` and `cd` commands:
* Every command you execute in the terminal takes place from the perspective of a certain directory, called your **working directory**.

* The **root directory** is the highest directory in the Linux hierarchy, and contains all other files and directories. It is denoted by `/`. Folders in the root directory cannot be modified without **root privileges** (see the `sudo` command for more details). NOTE: the root directory contains many important folders which should be kept as they are. Do not try and modify any of these folders unless you know what you're doing.

* Your **home directory** is the default location for all your personal files, and is located at `/home/<your-username>/`. Your home directory is the default working directory when you open the terminal for the first time.

## The `ls` command

The first command is the easiest - it simply lists all the files and directories in your working directory! Type in `ls` to see all the files in your home directory (since remember, each Terminal window opens into your home directory).

![ls](assets/commands/ls.png "ls")

If we type `ls <directory>`, we can list all the files in that directory. As an example, type `ls /`. You should be able to see all the folders in the root directory!

![ls /](assets/commands/ls-:.png "ls /")

We can add several optional flags to `ls` to change its output.

Adding `-a` to the command will print all files and directories, **including any hidden files**, in the working directory. (For more info on hidden files see the Hidden Files section later on). See that `.` and `..` are also printed; these are shortcuts that refer to the working directory and its parent directory respectively.

![ls -a](assets/commands/ls-a.png "ls -a")

Adding `-l` prints the list of files/directories in so-called long form. This prints information such as
* file permissions
* owner name
* owner’s group name
* file size (in bytes)
* date last modified

We explain how to read file permissions (e.g. `drwxr-xr-x`) in the File Permissions section later on.

![ls -l](assets/commands/ls-l.png "ls -l")

```
TIP: the up and down arrow keys can be used to scroll through previously used commands. This can save a lot of time when you eventually start using longer commands.
```

## The `cd` command

The `cd` command is used to change your current working directory. Type `cd <directory>` to switch to that directory.

For example, `cd /` changes our current working directory to the root directory. Now typing `ls` has the same effect as typing `ls /` from any other directory.

![cd](assets/commands/cd.png "cd")

That's it! You've learnt two of the most important Linux terminal commands.

## Relative and absolute directory paths

In the terminal, a directory path can be specified in two different ways:

An **absolute path** is given with reference to the root directory, and always begins with a `/`. For example, `/usr/local/bin/` is an absolute path. In contrast, a **relative path** is given with reference to the current working directory, and doesn’t begin with a `/`.

For example, say we have a file `file.txt` located in our `Desktop`, and our user is called `docsoc`.

![example directory](assets/example-directory.png "Example directory")
###### Our example directory structure

Let’s run through some scenarios:

The absolute path to `file.txt` is `/home/docsoc/Desktop/file.txt`.

If our current working directory is `/`, then the relative path to `file.txt` would be `home/docsoc/Desktop/file.txt`.

If our current working directory is `/home/`, then the relative path to `file.txt` would be `docsoc/Desktop/file.txt`.

If our current working directory is `/home/docsoc/` (remember this is the default working directory when you open terminal for the first time) then the relative path to `file.txt` would be `Desktop/file.txt`.

If our current working directory is `/home/docsoc/Desktop/`, then the relative path to `file.txt` would simply be `file.txt`.

Try experimenting more with the `ls` and `cd` commands, this time using both absolute and relative paths to specify directories.

## Terminal shortcuts

Terminal has some shortcuts that can be used instead of typing out long directory names:

* `~/` refers to your own home directory

* `.` refers to the current working directory

* `..` refers to its parent directory (i.e. one level higher up in the hierarchy)

These can be used in the `ls` and `cd` commands, and in general in any terminal command where a directory name is required.

## Hidden files

Files or directories that begin with `.` (a single dot) are hidden, and by default aren’t viewable to an ordinary user. Most hidden files and folders across the Linux filesystem are configuration files, e.g. the bash config file `.bashrc` and the `.git` folders inside git repositories. Hidden files can be viewed by using `ls -a`.

## File permissions

`ls -l` prints file permissions in a single 10-character string, e.g. `drwxr-xrw-`. Here we'll decipher what this means.

The first character will be `d` if the object in question is a directory, otherwise it will be `-` for a file.

The next 9 characters are all either `r`, `w` or `x`:
* `r` means the file/directory is readable
* `w` means the file/directory is writable
* `x` means the file/directory is executable
* if any of these are not present, a `-` will be present instead.

The first 3 characters describe permissions for the **owner** of the file.

The next 3 characters describe permissions for the **owner's user group**.

The last 3 characters describe permissions for **everyone else**.



For example, let's decipher `drwxr-xrw-`.

The first character is `d`, meaning this is a directory.

The next group of 3 characters is `rwx`. This means the owner has read, write and execute permissions.

The next group of 3 characters is `r-x`. This means everyone in the owner's user group can read and execute, but not write to the file.

The next group of 3 characters is `rw-`. This means everyone else can read and write, but not execute the file.

For information on how to change a file's permissions, see the `chmod` command.

# Advanced command line concepts

```
Brief (to be removed)

> (output to a file)
pipelining
```

These concepts are a little more complicated than your standard commands, so make sure you've experimented enough with commands you already know before moving on to these.

## Outputting to a file

So far we've looked at a few commands which print output to the terminal screen (e.g. `cat`, `grep`). In your forays through the Linux world you will encounter many more commands which also print useful information to the screen. But wouldn't it be nice to be able to send all of this output to a file instead, for example if the output is very long?

If you append `> <file>` (that's '>', followed by the name of a file) to the end of your command, output will be written to `file` instead of being printed to the screen, so you have a permanent copy of the command's output. Nifty!

For example, `grep -n "cats" catsdogs > cats` will find all the lines in `catsdogs` that contain the string "cats", and write their line numbers to the file `cats`.

## Streams

Every terminal command takes in some text input, and spits out some text output. These pieces of data are sent between the command and the Terminal using virtual input and output channels in your computer, called **streams** (also known as standard streams). There is a single input stream, called **stdin**, and there are two output streams, called **stdout** and **stderr**.

Stream | Purpose
  ---  |   ---
 stdin | Handling input for a command
stdout | Handing output for a command
stderr | Handling any error messages printed by the command

When executing a program as normal, all streams are connected to the Terminal. This means that any data to be input into a command must be typed into the Terminal, and the output of any command (along with any error messages) is printed to the Terminal.

### Pipelining

The pipelining technique allowed you to connect the **stdout** of one command to the **stdin** of another (called "piping"). In other words, you can tell the computer to run a second command using the output of the first one. This is done using the format `<first-command> | <second-command>` (`|` is the 'pipe' symbol).

For example, let's say we want to find all the files/directories in our working directory that contain the string "cat". We know a command which can list all the filenames in our working directory:

```
ls
```

And we know a command that can search for the string "cat" in a bunch of text:

```
grep -n "cat" <file>
```

We can pipe the output of `ls` into the input of `grep` like so:

```
ls | grep -n "cats"
```

This will print the names of all files/directories containing the string "cat". Note that the `<file>` argument is not needed for `grep` in this case; the Terminal is smart enough to realise input will come from the piped command instead.

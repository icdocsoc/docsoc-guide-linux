# Advanced command line concepts

```
Brief (to be removed)

> (output to a file)
streams (stdin, stdout and stderr) and pipelining
```
## Outputting to a file

So far we've looked at a few commands which print output to the terminal screen (e.g. `cat`, `grep`). In your forays through the Linux world you will encounter many more commands which also print useful information to the screen. But wouldn't it be nice to be able to send all of this output to a file instead, for example if the output is very long?

If you append `> <file>` to the end of your command, output will be written to `file` instead of being printed to the screen, so you have a permanent copy of the command's output. Nifty!

For example, `grep -n "cats" catsdogs > cats` will find all the lines in `catsdogs` that contain the string "cats", and write their line numbers to the file `cats`.

## Streams

## Pipelining

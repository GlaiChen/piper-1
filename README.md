# Piper

## Part A

The purpose is to simulate bash piping, e.g `ls -l /tmp | sort | head -n 2` by running `./piper "ls -l /tmp" "sort" "head -n 2"`.
The implementation is not perfect, specifically:
- When parsing every quote-enclosed command line, we allow up to 128 arguments, additional arguments won't be handled correctly.

## Part B

Consider the command `ps aux | grep pizza-margarita`.
Assuming there are no processes with the expression `pizza-margarita` in them, the expected output from this command is an empty string.
Why? Because all the output from `ps aux` is sent through a pipe as input into the `grep` command, which in turn filters and prints
only the lines matching the specified expression. In this case, there are none that match, so the output is empty.

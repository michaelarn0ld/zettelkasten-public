# Understanding Stdin, Stdout, Stderr
*When you enter a command, if no file name is given, your keyboard is the 
standard input (stdin).
*Your screen is standard output (stdout); by default, commands take input from
stdin and send the results (if any) to stdout.
*Standard error (stderr) is where error messages go; by default, this is your
screen.


## Pipes and Stdin
The power of UNIX comes from the ability to chain (pipe) the stdout of one
program to the stdin of another.
```bash
grep '#' README.md | sed 's/\#* //' | nl | more
```
1. Grab all the lines from ```README.md``` that contain '#' (in quotes because
it indicates a comment in bash) and pipe to ```sed```
1. Substitute any '#' and a space for nothing and pipe to ```nl```
1. Inject line numbers at the beginning of each line and pipe to ```more```
1. ```stdout``` from ```more``` makes it to the screen


## Redirecting Stdout and Stderr
```bash
find / > find.out 2>found.err
```

This command ***finds*** all files recursively from ```/```, redirects
```stdout``` to ```find.out``` and redirects ```stderr``` to ```found.err```. It
is exactly equivalent to:
```bash
find / 1>find.out 2>found.err
```

Stdout has file descriptor 1 and stderr has file descriptor 2.

If you would like to write both the ```stdout``` and the ```stderr``` to the 
same place:
```bash
find / > find.both 2>&1
```

This translates to:
*Send ```stdout``` to ```find.both```
*Send ```stderr``` to ```stdout```


## Related
[202110050353](../202110050353) - Exploring Links (ln) in Linux


## Tags
#linux

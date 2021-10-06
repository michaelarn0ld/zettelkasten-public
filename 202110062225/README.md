# Shell Scripting, Interpretting, and Running Processes
Imagine you have written a command to list the titles of all your zettels:
```sh
head -1 $ZETDIR/*/README.md |grep '#' |sed 's/#//' |sed 's/\s//'
```

By redirecting it to a file ```foobar```, you can easily create a reusable
script:
```sh
echo "head -1 $ZETDIR/*/README.md |grep '#' |sed 's/#//' |sed 's/\s//'" > foobar
```

You can check the permissions of the script file:
```sh
$ ls -l foobar
----------------------------------------------------
-rw-rw-r-- 1 michael michael 104 Oct  6 17:58 foobar
```

By default, the file only has read/write permissions; it is not excecutable.
If we want to add execution permissions to the file:
```sh
chmod +x foobar
```

For this case, we will not add execution permissions so we have an idea of what
happens when the script becomes a ***process***. You want to be able to inspect
the process:
```sh
chmod -x foobar
echo "while true; do sleep 2; done" >> foobar"
```

Now, use POSIX shell to interpret the file and create a process:
```sh
sh foobar
```

Check the running process:
```sh
$ ps -ef |grep foobar


michael    17514   16618  0 18:05 pts/1    00:00:00 sh foobar
michael    17588   17524  0 18:07 pts/2    00:00:00 grep --color=always foobar
```

Navigate to the virtual filesystem where the process information is stored:
```sh
cd /proc/17514/
```

All the information in this directory will provide information as to how
```sh foobar``` was called. For example:
```sh
ls -l cwd
-----------------------------------------------------------------
lrwxrwxrwx 1 michael michael 0 Oct  6 18:08 cwd -> /home/michael/
```

This shows your the directory from where the process originated. It is important
to realize that ```foobar``` itself was not called. The interpretter (in this
case ```sh```) is what run and converts the commands into machine language that
can run. In reality, it converts the source code into system calls which are 
interpretted by the kernel and converted to binary which gets sent to the
device.


## Related
[202110050602](../202110050602) - Understanding Stdin, Stdout, Stderr
[202110051756](../202110051756) - Create and Manage Users and Groups
[202110052020](../202110052020) - Changing File Permissions


## Tags
#linux #bash #shell #processes

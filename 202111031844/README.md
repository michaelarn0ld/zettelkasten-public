# Working with Delimited Data
Data can be delimited in all sorts of fashions that make it convenient to work
with in shell scripting (or other programming languages). Some of the most
common delimiters include whitespace, tabs, bars, or commas.

Delimiters are useful for splitting data up. Consider the following piece of
data:
```
Michael 23
Adi 23
Oliver 2
Rex 8
Linguine 1
```

If this data was stored in a file called ```users.txt``` and we wanted to print
out each row of data (each containing two fields), we would write:

```
while read -r user; do
    printf "%s%s\n" $user
done < user.txt
```

By default, shell interprets whitespace as the delimiter. If you wish to change
this, you can set the internal field seperator to anything you want; for
example, if you wanted to change the deault delimiter to a bar:
```
IFS=|
```

Now, if we repeat the previous example, all the rows from the text file will
appear on the same line because we no longer use whitespace as a delimiter. This
means that each ```%s``` from the format string will have no place to terminate,
so the new line escape will never be reached.


## Related
[202110050353](../202110050353) - Exploring Links (ln) in Linux
[202110050602](../202110050602) - Understanding Stdin, Stdout, Stderr
[202110051756](../202110051756) - Create and Manage Users and Groups
[202110052020](../202110052020) - Changing File Permissions
[202110062225](../202110062225) - Shell Scripting, Interpretting, and Running Processes
[202111011559](../202111011559) - ANSI Escapes and Colors
[202110062225](../202110062225) - Shell Scripting, Interpretting, and Running Processes


## Tags
#linux #shell #bash

# ANSI Escapes and Colors
ANSI escapes are used to control cursor location, color, font styling, and other
options on video text terminals and terminal emulators. Certain sequences of
bytes, most starting with an ASCII escape character and a bracket character, are
embedded into text.

Check out the following examples that use ```printf``` to print out all the
major colors to the screen:

```sh
for i in `seq 30 37`
    do printf "\e[${i}m%s\n" "Hello, ANSI"
done
```

We can easily change the font weight from normal to bold by modifying to escape
sequence from ```\e[${i}m``` to ```\e[1;${i}m```


## Related
[202109270322](../202109270322) - Exploring the Differences between *.bashrc* and *.profile*
[202110050353](../202110050353) - Exploring Links (ln) in Linux
[202110050602](../202110050602) - Understanding Stdin, Stdout, Stderr
[202110051756](../202110051756) - Create and Manage Users and Groups
[202110052020](../202110052020) - Changing File Permissions
[202110062225](../202110062225) - Shell Scripting, Interpretting, and Running Processes
[202110090443](../202110090443) - Shell Tips: Use 'bc' as a Calculator


## Tags
#shell #linux

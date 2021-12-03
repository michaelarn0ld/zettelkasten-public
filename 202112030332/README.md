# Navigating Files in Vim

|   Commands    |   Summary
|   :-:         |   -
|   :e          |   run this command and press ```tab``` to open a file tree
|   :b          |   looks for files in the buffer
|   :b <match>  |   only offers files in buffer with some matching expression
|   :bn         |   go to the next file in the buffer list
|   :bp         |   go to the previous file in the buffer list

To navigate natively, it might be a good idea to boot vim in the root directory
of the project and then use the ```:e <Tab>``` command to start adding files to
the buffer. Once we have enough files we're working with, we can use the short
```:b``` commands.

## Related
[202109270322](../202109270322) - Exploring the Differences between *.bashrc* and *.profile*
[202110050353](../202110050353) - Exploring Links (ln) in Linux
[202110050602](../202110050602) - Understanding Stdin, Stdout, Stderr
[202110062225](../202110062225) - Shell Scripting, Interpretting, and Running Processes
[202111011559](../202111011559) - ANSI Escapes and Colors
[202111031844](../202111031844) - Working with Delimited Data

## Tags
#linux

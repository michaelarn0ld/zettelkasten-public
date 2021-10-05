# Exploring Links (ln) in Unix
The ```ln``` command is used to create links between files.
```bash
ln [OPTION] target_file link_name
```
There are two primary ways to do this: hard links and symbolic links.


## Hard Links
```bash
ln target_file link_name
```
 A hard link is a direct reference to a target file via its place in memory.
 The hard and the target file point to the exact same place; consequentially, 
 you can delete one without deleting the other. Changes made to one will also be
 reflected in the other. Unlike a symbolic link, moving it to another directory
 will also not affect the link. 


## Symbolic Links
```bash
ln -s target_file link_name
```
Symbolic links are essentially shortcuts that reference to a file instead of its
place in memory. Since the symbolic link is referring ***to the file***,
changing the directory of the file will break the symbolic link.


## Tags
#linux

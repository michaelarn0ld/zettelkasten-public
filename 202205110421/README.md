# Bash: Special Workflows

## Change Directory to the Path of Executable Easily
Sometimes, you want to inspect some executable. Instead of the normal way to
navigate the file system, here is the easy way to navigate to its directory:
```
cd $(which [EXECUTABLE_ON_PATH] | sed 's|\(.*\)/.*|\1|')
```
Alternatively, if you just want to edit the file, you can do so like this:
```
vi $(which [EXECUTABLE_ON_PATH])
```


## Related
[202110090443](../202110090443) - Shell Tips: Use 'bc' as a Calculator
[202111031844](../202111031844) - Working with Delimited Data
[202111011559](../202111011559) - ANSI Escapes and Colors


## Tags
#bash

# Using Regular Expressions in Bash
Let's say you wanted to iterate over a file and you wanted to perform some 
operations on all files except those with `.json` or `.sh` extensions. You could 
have a script like:
```sh
#!/bin/bash

do_some_operation() {
  # some implementation for this function
}

for file in *; do
  if [[ $file =~ ^.*(.json|.sh)$ ]]; then
    continue
  fi
  do_some_operation $file
done
```

## Related
[202109270322](../202109270322) - Exploring the Differences between *.bashrc* and *.profile* \
[202111031844](../202111031844) - Working with Delimited Data \
[202205110421](../202205110421) - Bash: Special Workflows

## Tags
#bash

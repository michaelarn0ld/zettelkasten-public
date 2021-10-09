# Shell Tips: Use 'bc' as a Calculator
```sh
$ echo 'scale=5; 3/4' | bc

--------------------------

.75000
```

* The ```scale``` refers to the number of significant digits
* When ' ' are used insead of " " it means that the expression within is
evaluated as a string literal. Use " " when there are variables involved.


## Related
[202110062225](../202110062225) - Shell Scripting, Interpretting, and Running Processes


## Tags
#bash #shell

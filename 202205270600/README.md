# Java: Heap Dump

## Why Heap Dump
Let's say you have a java program and you notice that the memory utilization
for it is slowly growing, even though other conditions are not changing. You 
may have a memory leak in the program. 

In this case, it will be a great idea to perform a heap dump!

## How Heap Dump
```
jmap -dump:[live],format=b,file=<file-path> <pid>
```

* `live` - if set, it only prints objects which have active references and 
   discards the ones that are ready to be garbage collected. This parameter is
   optional.
* `b` - dump file will be binary format, if not included, the result is the same
* `file-path` - where the dump goes
* `pid` - java process we want to heap dump

## Tags
#java #heap #memory

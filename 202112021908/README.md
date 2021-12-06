# Java: References or Copies?

Q: Say I have a void method that takes an integer parameter. If I manipulate the
parameter inside of the void method, will the variable from the caller also be
manipulated?

```java
public static void main(String[] args) {
    int i = 0;
    addOne(i);
    // i = 0 or i = 1 ?
}

public static void addOne(int input) {
      input++;
}
```

A: The answer is no, the variable from the caller will not be manipulated. In
the example above, the value of ```int i``` will be ```0``` after the call.
In java, ***all values*** are  passed by ***copy***; however, objects can be
manipulated with methods in place. Strings are an exception! Strings are
immutable! Even if we have a ```s.reverse()``` method, we would need to approach
it as ```s = s.reverse()``` to reallocate the memory for the return of the the
```s.reverse()``` method.

When you pass a reference type as a parameter to a f(x), the value that is being
copied is its ***memory reference***. The original reference and the parameter
reference are different but they point to the same spot in memory. Thus, when
we make a change to the reference parameter, the change is seen in both the
original and the reference.

There are some similarities! If we assign a ***new value*** to the reference
parameter, then the reference parameter and the original reference no longer
point to the same place in memory. Therefore, ***if we change the assignment
on a reference parameter***, any changes thereafter will have on affect on the
original reference's memory.


## Related
[202111300552](../202111300552) - Java: Questions on Strings
[202112021908](../202112021908) - Java: References or Copies?
[202112061553](../202112061553) - Java: Intro to OOP
[202112061620](../202112061620) - Java: Class Syntax


## Tags
#java

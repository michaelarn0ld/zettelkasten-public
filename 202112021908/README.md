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

A: In java, ***everything*** is passed by ***copy***; however, objects can be
manipulated with methods in place. Strings are an exception! Strings are
immutable! Even if we have a ```s.reverse()``` method, we would need to approach
it as ```s = s.reverse()``` to reallocate the memory for the return of the the
```s.reverse()``` method.


## Related
[202111300552](../202111300552) - Java: Questions on Strings


## Tags
#java

# Java: Class Syntax

The syntax for a class defintion is an optional access modifier, the class
keyword, a name, and a code block.
```[access modifier] class [name] {
}```

A class level variable is defined and optionally assigned inside of a class
code block
``` [acess modifier] [type] [name];```

A constructor is a method-like subroutine that ensures an object is instantiated
in a valid state.
```[access modifier] [class name] ([type][parameter 1],...,[type][parameter n]) {
}```
In a similar fashion to methods, constructors can also be overloaded. You may
have more than one constructor for a class, but each constructor must have a 
unique combination of parameters.


## Methods and Classes

We can omit the ```static``` keyword for most methods. Non-static methods have
access to fields while static methods don't. Static methods are independent with
no class context. Non-static methods cannot be excecuted independently, they
are part of an object and have access to its state.


## Access Modifiers + Getters & Setters

* ```public``` -> all classes can access the member
* ```protected``` -> only classes in the same package can access the member
* ```private``` -> the member is only visible from the inside the class containing
                   the definition

To prevent well-intentioned devs from accidentally putting an instance of an
object into an invalid state, we can make the fields we do not want them to
access ```private```. When we do this, the only way for them to interact with
those fields is through methods (getters and setters) that they can access.

The ```final``` keyword may appear after an access modifier. If this optional
keyword is used then it means that once the value for the field is recieved
during construction, then it can no longer change; after this point it is read
only!


## Related
[202111300552](../202111300552) - Java: Questions on Strings
[202112021908](../202112021908) - Java: References or Copies?
[202112061553](../202112061553) - Java: Intro to OOP


## Tags
#java

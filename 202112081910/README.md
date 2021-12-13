# Java: On Static Methods and Non-Static State
In Java, a ***non-static*** method have access to ***both*** static and
non-static state; however, a ***static method*** has access only to
***static state***. It can not change non-static state (unless an instance of
the class is a parameter of the method) because a static method exists outside
the context of any individual instance of an object. 


## Related
[202112061553](../202112061553) - Java: Intro to OOP\
[202112061620](../202112061620) - Java: Class Syntax\
[202112080538](../202112080538) - Java: Questions on Inheritance\
[202112080610](../202112080610) - Java: On Using Interfaces\
[202112080626](../202112080626) - Java: 4 Pillars of OOP


## Tags
#java

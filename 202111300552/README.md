# Java: Questions on Strings

Q: Is a string variable just a pointer to a sequence of characters underneath
the hood? \
A: Yes

Q: On a 64-bit computer, does this mean that the maximum size that any given
primitive type can be allocated is 64 bits? How is this related to the size of
the "word"? \
A: The words are 64-bits, multiple variables might be able to fit into the same
word but have an offset in their address if their type is small enough.

Q: How much memory is allocated to char; How is this related to its address in
memory and how the string accesses it? If there are 12 characters in a string,
does this mean that the string can access 12 different addresses in memory? \
A: The chars of the string will be stored in 3 words; each char is addressed to
the word + an offset from where it is at in memory.

Q: The default value for reference types is null; does this mean that a reference
type that is declared but not assigned a value is null? What about primitive types?
What are their default values? \
A: bool -> false, double -> 0.0, int -> 0

Q: Does the String.replace(this, withThat) method replace all instances of "this"
with "withThat"? \
A: yes

Q: Say there is int a = 8 and int b = 8; we may say that a == b evaluates true;
does this mean that a comparison on primitive types compares values and not
position in memory? Similarly, does this imply that ***all*** reference types
are strictly equal if and only if they reference the same space in memory? \
A: Reference types compare the reference addresses while primitive types
compare the actual values/


## Related
[202112021908](../202112021908) - Java: References or Copies?


## Tags
#java

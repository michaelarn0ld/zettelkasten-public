# Bitwise Operators
|   Operator   |   Summary         |   Example
|   :-:        |   -               |   -
|   &          |   bitwise AND     |   5 & 9 = 1     -> 00101 & 01001 = 00001  |
|   \|         |   bitwise OR      |   5 \| 9 = 13    -> 00101 \| 01001 = 01101|
|   ^          |   bitwise XOR     |   5 ^ 9 = 12    -> 00101 ^ 01001 = 01100  |
|   &^         |   bitwise clear   |   5 &^ 9 = 0    -> 00101 &^ 01001 = 00100 |
|   <<         |   left shift      |   5 << 1 = 10   -> 00101 << 1 = 01010     |
|   >>         |   right shift     |   5 >> 1 = 2    -> 00101 >> 1 = 00010     |

Bitwise clear deserves a little deeper explanation because it is not immediately
clear what is going on:
* 5 &^ 9 = 5 & (5 ^ 9)
* 00000101 & (00000101 ^ 00001001)
* 00000101 & 00001100 = 00000100


## Related
[202110090311](../202110090311) - Newton-Raphson Method


## Tags
#go #computerscience

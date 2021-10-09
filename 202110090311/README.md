# Newton-Raphson Method
Numerical methods can be distinguised from other branches of analysis and
computer science by three characteristics:
* They work with arbitrary real numbers
* We are concerned not only with the correctness and existence of a solution,
but with the resources required to compute the result
* We are concerned with the accuracy of the results, because in practice we will
only ever have approximate answers


## Square Roots
The classic algorithm to illustrate these concerns is the
***Newton-Raphson Method*** to compute square roots:
```
x = sqrt(a) for a > 0

which is to solve

x^2 = a
```

Say we have some function:
```
f(x) = x^2 - a
```

Let us also assume so arbitrary approximation for the solution:

```
f(x_n) ~ 0
```

Take the tangent line of this point recalling:
```
y - y_1 = m(x - x_1) where m = f'(x_n) and y_1 = f(x_n)
```

The resulting line has the form of:
```
y = f(x_n) + f'(x_n)(x - x_n)
```

The point, x_n+1 where this tangent intersects the x-axis is said to be a better
approximation for the solution:
```
0 = f(x_n) + f'(x_n)(x_n+1 - x_n)
x_n+1 = x_n - f(x_n)/f'(x_n)
```

Replacing with the function f(x) we are using to solve the square we get:
```
x_n+1 = x_n - (x_n^2 - a)/(2x_n)

```

We can iterate over this process to get a pretty good approximation for the
square root of a number:
```go
func squareRoot(a float64) float64 {
    x := 1                // an arbitrary start for approximation, not optimized
    for i := 0; i < 10; i++ {      // arbitrary amount of iterations
        x -= (x*x - a)/(2*x)
    }
    return x
}
```


## Related
[202110071918](../202110071918) - Bitwise Operators


## Tags
#computerscience

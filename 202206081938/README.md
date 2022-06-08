# Python Type Annotations
Without type annotation:
```python
num = 5
word = "hello"

def add(x, y):
  return x + y

new_val = add(2, 3)
```

With type annotation:
```python
num: int = 5
word: str = "hello"

def add(x: int, y: int) -> int:
  return x + y

new_val: int = add(2, 3);
```

## Tags
#python

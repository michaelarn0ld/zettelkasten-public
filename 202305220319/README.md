# Clean Code: Functions

## Summary
* Functions should be small
* They should do only one thing and do it well
* There should be one level of abstraction per function. Concepts within the
  function should be at the same level of abstraction
* Functions should use painfully descriptive names
* You should seek to minimize the number of arguments in a function; prefer one
  or two. If you are using three, consider if its neccessary. More than 3 is a 
  code smell
* Passing a boolean into a function is a code smell
* When a function seems to have more than 2 or 3 arguments, consider wrapping the
  args into their own class (if they are part of the same concept)
* Functions should have no side effects
* Prefer exceptions to returning error codes; remember that error handling is a
  single thing!
* Writing code is like any other form of formal writing. You write it, then with
  a bit of wordsmithing, you form it, shape it, and eventually craft it to its
  final form. You should not expect to write functions perfectly to start, you
  refactor the code until it best adheres to the above rules.

## Tags
#computerscience

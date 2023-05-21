# Clean Code: Naming Things

## Summary
* Use intention-revelaing names; your names of variables, functions, classes, etc
  should invoke a sense of the purpose of that technical artifact.
* Avoid leaving false clues in your names; do not refer to a grouping of accounts
  as an `accountList` unless it is actually `List`
* Make meaningful distinctions in the naming of things; noise words are redundant.
  Name things in a way that provides clues to the authors intention, especially
  when two artifacts are technically (typed) similar and exist in the same scope.
* Use easily pronouncable names
* Use easily searchable names
* Avoid encodings in the naming of things; names of artifacts should convey the
  author's intent clearly to all who read it, even if the reader was outside of
  the orginization.
* Do not prefix interfaces with `IFooFactory`. The proceeding `I` is distracting.
  Users should not know if they are using an interface.
* Avoid mental mapping; readers should not have ti translate your names into 
  names they already know. Clarity is king
* When constructors are overloaded; use static factory methods with names that
  describe the arguments. Pro-tip: consider enforcing their use by making the
  corresponding constructors private
* Pick one word, for the entire codebase, per concept. It is confusing to have
  different methods prefixed with `fetch`, `retrieve`, `get` that all represent
  the same abstract idea. Choose one and stick with it.
* Avoid using the same word for more than one purpose; if you have methods in
  different classes called `add` that basically concatenate one value to another
  or mathematically add on value to another, then do not have another `add` method
  in the codebase that inserts a value into some collection. Instead, you should
  call this method `append` or `insert`.
* Use computer-science-y terms whenever possible; we call thes solution domain
  names. If you have a series of jobs that are executed in a LIFO way, then it
  makes sense to call the collection of those jobs as a `JobQueue`
* When solution domain names do not exist for the problem you are solving, then
  use problem domain names
* Add context to the names of artifacts when it is required

## Tags
#computerscience

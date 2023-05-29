# Clean Code: Comments
* Use comments when you cannot find a variable name, function name, coding
  structure, or other tool to make a point, and its intent, clear.
* Use comments to give context and inform intent of low-level abstractions or
  in other places where the tools of the language are not adaquate to describe
  what the source code does.
* Use Javadocs (or other language equivalent) for publicly consumed APIs; a public
  API is one that is intended to be externally consumed. This means you should 
  only write Javadocs for code that will consumed outside of the repository in
  which it is written.
* Avoid "TODO" comments, prefer JIRAs with the proper context of exactly what 
  needs to be done instead.
* Avoid redundant comments that basically just explain the source code. The cod.e
  itself should be self-documenting
* Avoid noise comments which just restate the obvious and provides no new info.
* Avoid position markers which collect functions/methods of a specific intent
  under a banner. EX) "// ACTIONS //////////////////" proceeding a collections
  of methods that do some action -> this would be a bad comment in the code.
* Avoid too much information in your comments. Don't put historical descriptions
  or other discussions into the comments.

## Tags
#computerscience

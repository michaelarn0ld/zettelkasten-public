# Technical Interview Guidelines II

## Techniques for Solving Problems

### DIY (Do it Yourself)
* Before you start coding, think of a large example of the problem and 
intuitively - manually, that is - solve it for a specific example
* Think about how you solved it with your brain and reverse engineer your
approach

### Simplify and Generalize
* Example: A ransom note can be formed by cutting words out of a magazine to
form a new sentence; given a ransom note and a magazine, determine if it is
possible to create the note from the magazine.
* Simplify the above to this: A string is formed from characters; given a two
strings a and b, determine if it is possible that b could be formed by using the
characters from a
* Approach: iterate through a and store the frequency of all characters in a 
hash map; then use the results from this to determine if string b uses only 
characters in a at less than or equal to the appropriate frequency.
* SIMPLIFY & GENERALIZE: We modified the problem so we are cutting characters out of a magazine 
    instead of whole words (simplify)

## Tags
#interview

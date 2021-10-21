# Interesting Details of Inline HTML Elements
Inline elements do not alter the flow of content by adding new lines after the
closing tag. These elements are most commonly used to alter the content
within a block element.


## Anchor
* ```<a>``` is the tagname
* ```href="http://www.google.com"``` attribute store information for hyperlink
* ```href="#section2"``` navigates to element with ```id=section2```
* ```href="/about"``` navigates to relative path at ```/about```
* ```target="_blank"``` opens link in a new tab or window
* ```<a target="_blank" href="http://www.google.com"><img src="path/to/img"
alt="Some Description"></a>``` This is how to make a clickable image link


## Strong/Bring to Attention
* <strong> indicates elements with strong importance
* <b> this stands for "bring to attention" and is semantically different from
strong


## Line Break
* <br> to produce a line break in your content


## Code
* <code> to show that content is computer code; content is shown as monospace
font


## Emphasis/Italics
* <em> is used to emphasize a word or a phrase
* <i> is used to off-set text from normal prose for readability reasons


## IFrames
* <iframe> allows you to embed another HTML page into the current one; this is
where "_top" and "_parent" attribute links can come into play.
* Not good for performance


## No Script
* <noscript> defines a section of HTML only to be displayed when the browser
has disabled JS


## Big/Small
* <big> and <small> change the font size of the content by 1 in either direction


## Span
* <span> is essentially the <div> of inline elements; has no impact on the 
content it contains unless it is styled with CSS


## Superscript/Subscript
* <sub> and <sup> are used for subscripts and superscripts respectively; very
helpful for math or chemistry formulas


## Special Characters
|   Character   |   Code to Use
|   :-:         |   -
|               |   &nbsp;
|   <           |   &lt;
|   >           |   &gt;
|   &           |   &amp;
|   "           |   &quot;
|   '           |   &apos;
|   ©           |   &copy;
|   ®           |   &reg;

## Related
[202110210320](../202110210320) - Semantic HTML Block Elements


## Tags
#webdev

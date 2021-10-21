# Semantic HTML Block Elements
Block level elements create a visible block on the page which means that they
create a new line after their content is rendered. Block elements stack on top
of each other


## Headings
There are six levels of headings available in HTML; each has a an associated
number ```<h1>, <h2>, <h3>, <h4>, <h5>, <h6>```. The heading are hierarchical
with ```<h1>``` being the main heading and the other heading levels nested
inside each other in numerical order to maintain sensible structure in the 
document


## Paragraphs
Paragraph tags, ```<p>``` seperate blocks of text. By default, browser put a
single line break in between paragraphs to give them some white space. Breaking
the page into paragraphs helps with accessibility because it helps screen
readers navigate the content. Don't use empty paragraphs to create additional
white space


## Division
Division tags, ```<div>``` are generic block level containers. They have no
useful effect on the content or layout of a page unless they are styled by CSS


## Preformatted
Preformatted tags, ```<pre>``` are used for content that is preformatted and
should be displayed exactly as written in the HTML file with regards to
whitespace; this is great for displaying source code on the page where tabs
and indentations really matter


## Block Quotation
Blockquote tags, ```<blockquote>``` are used for extended quotations. You can
use the cite attribute to provide a link to source and the ```<footer>``` to
provide the author for the quote


## Lists
Unordered list tags are, ```<ul>```; ordered list tags are ```<ol>```. For both
cases, each list item is contained in the tags ```<li>```. Additionally, lists
can be nested within each other to create sublists.

Another type of list is description list, ```<dl>```.  These are common for
dictionaries where each term is given the tag ```<dt>``` and its subsequent
description is given the tag ```<dd>```


## Figures and Captions
Figure tags, ```<figure>``` are newer and are used to group self-contained
content with the optional ```<figcaption>``` so that you can refer to the
figure and its caption as a single unit with CSS or JS.


## Fieldsets
Fieldset tags, ```<fieldset>``` are used to group controls like checkboxes or
radio buttons. Within this element, you can provide the ```<legend>``` that
gives a caption for the fieldset


## HTML5 Content Separators
There are plenty of other tags in the HTML5 spec that authors use to
semantically seperate HTML elements in order to make selection easier. These do
not add any visual flare and they will always contain one or more child elements
that are standard HTML.

|   Tag         |   Description
|   :-:         |   -
|   <address>   |   wraps content that contains contact information
|   <aside>     |   wraps elemtents that are indirectly related to the documents main content
|   <footer>    |   wraps elements that make up footer of a document
|   <header>    |   wraps elements that contain introductory information
|   <nav>       |   wraps content for navigation links (top bar or side bar)
|   <main>      |   wraps content that are the main content of the document
|   <article>   |   wraps content that might be independently distributed (blog or forum post)
|   <selection> |   wraps a heading and some content (wrap each deptartment and its employees in a section)


## Related
[202110210421](../202110210421) - Interesting Details of Inline HTML Elements

## Tags
#webdev

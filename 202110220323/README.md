# CSS Styling: Tables and Forms
By default, the content styling in tables and forms is uninspiring; however,
with the power of CSS, we are able to make beautiful pages that improve user
experience.


## Tables
Consider the following table:
```html
<table>
    <caption>List of Best Selling Games (not bundled with console)</caption>
    <thead>
        <tr>
            <th>Title</th>
            <th>Sales</th>
            <th>Initial Release</th>
            <th>Publisher</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Minecraft</td>
            <td>180,000,000</td>
            <td>2011</td>
            <td>Mojang</td>
        </tr>
        <tr>
            <td>Grand Theft Auto V</td>
            <td>120,000,000</td>
            <td>2013</td>
            <td>Rockstar Games</td>
        </tr>
        <tr>
            <td>PlayerUnknown's Battlegrounds</td>
            <td>60,000,000</td>
            <td>2017</td>
            <td>PUBG Corporation</td>
        </tr>
        <tr>
            <td>Pokemon Red / Green</td>
            <td>47,520,000</td>
            <td>1996</td>
            <td>Nintendo</td>
        </tr>
        <tr>
            <td>Mario Kart Wii</td>
            <td>37,240,000</td>
            <td>2008</td>
            <td>Nintendo</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th scope="row">Total Sales</th>
            <td>444,760,000</td>
            <td></td>
            <td></td>
        </tr>
    </tfoot>
</table>
```
By default, this table is pretty bland; however, one of the easiest ways we can
improve it is by adding some spacing:
```css
table {
    table-layout: fixed;
    width: 100%;
    border-collapse: collapse;
    border: 3px solid black;
}

thead th:nth-child(1) {
    width: 25%;
}

thead th:nth-child(2) {
    width: 15%;
}

thead th:nth-child(3) {
    width: 15%;
}

thead th:nth-child(4) {
    width: 25%;
}

th, td {
    padding: 20px;
}
```
Here, we introduced a few new CSS properties. ```table-layout: fixed``` prevents
the columns from beings sized by the content they contain. This led us to use
the descendent selector ```nth-child(n)``` to give each column a percentage
based width. By setting the table width to 100%, it will scale nicely to fit 
different screen sizes.

We also used the ```border-collapse: collapse``` property to remove space
between cells borders, which by default have some amount of seperating
whitespace.

Let's adjust the styling of the table's text:
```css
th, td {
    padding: 20px;
    letter-spacing: 1px;
}

html {
    font-family: helvetica, arial, sans-serif;
}

tbody tr td:nth-child(1) {
    text-align: left;
}

tbody tr td:nth-child(2) {
    text-align: center;
}

tbody tr td:nth-child(3) {
    text-align: center;
}

tbody tr td:nth-child(4) {
    text-align: left;
}

tfoot th {
    text-align: right;
}

tfoot td {
    text-align: center;
}
```

We can also add some color to the table:
```css
tbody tr:nth-child(even) {
    background-color: gainsboro;
}

thead tr {
    background-color: black;
    color: white;
}

tfoot tr {
    background-color: black;
    color: white;
}
```

Finally, let us style the caption:
```css
caption {
    padding: 20px;
    font-style: italic;
    color: darkblue;
    caption-side: bottom;
    text-align: right;
    letter-spacing: 1px;
}
```
Here. the ```caption-side``` property allows us to the move the caption to the
bottom and out ```text-align: right``` pushs the text to the right edge of the
parent element (which is the table itself).


## Forms
Consider the following web form:
```html
<form>
    <div>
        <label for="name">Name</label>
        <input type="text" id="name" name="name">
    </div>
    <div>
        <label for="email">Email</label>
        <input type="email" id="email" name="email">
    </div>
    <div>
        <label for="source">Referral Source</label>
        <select id="source" name="source">
            <option>Google</option>
            <option>Bing</option>
            <option>Mail</option>
            <option>Conference</option>
            <option>Customer Referral</option>
        </select>
    </div>
    <div>
        <label for="comments">Comments</label>
        <textarea id="comments" name="comments"></textarea>
    </div>
    <div>
        <button>Submit</button>
    </div>
</form>
```

The first thing we should do is "reset" the form controls. We will remove all
of the browser-dependent form styling so that we have a more consistent UX
across browsers.
```css
button,
input,
select,
textarea {
  font-family: inherit;
  font-size: 100%;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

textarea {
  overflow: auto;
}
```
By setting the ```font-family: inherit``` and ```font-size: 100%;``` we are able
to force controls to user our defined font instead of whatever the browser
defaults to. The ```border-box``` allows us to ovveride the standard box model
from our previous lesson such that the width of the box is the width of the
visible box on the page. Setting ```overflow: auto;``` instructs the browser
to only show scrollbars if they are neccessary to fit the content.

Now, let's style the controls
```css
form {
    max-width: 500px;
    padding: 20px;
    font-size: 13px;
    font-family: Helvetica, Arial, sans-serif;
}

label {
    display: inline-block;
    width: 25%;
    font-weight: bold;
}

input[type="text"],
input[type="email"],
select,
textarea {
    border: 1px solid #c2c2c2;
    box-shadow: 1px 1px 4px #ebebeb;
    border-radius: 3px;
    padding: 7px;
    outline: none;
    width: 70%;
}

form div {
    margin-bottom: 10px;
}
```
These are the basics; with this we have given font settings to the entire form,
bolded the labels, styled the inputs and rounded their edges. and given the
divs that contain each control some breathing room. 

If we want to take it to the next level:
```css
.submit-row {
    text-align: center;
}

.submit-row button {
    border: none;
    padding: 8px 15px 8px 15px;
    background: #FF8500;
    color: #fff;
    box-shadow: 1px 1px 4px #DADADA;
    border-radius: 3px;
}

.submit-row button:hover {
    background: #EA7B00;
}
```
This makes our button a little prettier, but we need to add 
```class=submit-row``` to the parent div of the button!

## Tags
#webdev

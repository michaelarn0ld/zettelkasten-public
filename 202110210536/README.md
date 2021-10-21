# HTML Tables: Quick Tips


## Basics of Table Elements
For a table, ```<table>``` is the parent element tag that will contain all the 
child rows and columns. Table headers are ```<th>```, rows are ```<tr>```, and
columns are ```<td>```. Consider the following table:

|               |   Q1      |   Q2      |   Q3      |   Q4
|   :-:         |   -       |   -       |   -       |   -
|   Electronics |   $35M    |   $33M    |   $37M    |   $40M
|   Furniture   |   $20M    |   $23M    |   $18M    |   $27M
|   Clothing    |   $15M    |   $17M    |   $13M    |   $35M

In HTML, this is represented as:
```html
<table>
    <tr>
        <th></th>
        <th>Q1</th>
        <th>Q2</th>
        <th>Q3</th>
        <th>Q4</th>
    </tr>
    <tr>
        <th>Electronics</th>
        <td>$35M</td>
        <td>$33M</td>
        <td>$37M</td>
        <td>$40M</td>
    </tr>
    <tr>
        <th>Clothing</th>
        <td>$20M</td>
        <td>$23M</td>
        <td>$18M</td>
        <td>$27M</td>
    </tr>
    <tr>
        <th>Furniture</th>
        <td>$15M</td>
        <td>$17M</td>
        <td>$13M</td>
        <td>$15M</td>
    </tr>
</table>
```

## Spanning Rows and Columns
If we want a cell to span multiple rows or columns, we  can use the rowspan or
colspan attributes:
```html
<table>
    <tr>
        <th>Element</th>
        <th>Spell</th>
    </tr>
    <tr>
        <th rowspan="2">Fire</th>
        <td>Burning Palm</td>
    </tr>
    <tr>
        <td>Fireball</td>
    </tr>
    <tr>
        <th rowspan="3">Water</th>
        <td>Healing Rain</td>
    </tr>
    <tr>
        <td>Ice Block</td>
    </tr>
    <tr>
        <td>Frost Orb</td>
    </tr>
</table>
```
```html
<table>
    <tr>
        <th></th>
        <th>Q1</th>
        <th>Q2</th>
        <th>Q3</th>
        <th>Q4</th>
    </tr>
    <tr>
        <th>Electronics</th>
        <td>$35M</td>
        <td>$33M</td>
        <td>$37M</td>
        <td>$40M</td>
    </tr>
    <tr>
        <th>Clothing</th>
        <td>$20M</td>
        <td>$23M</td>
        <td>$18M</td>
        <td>$27M</td>
    </tr>
    <tr>
        <th>Furniture</th>
        <td>$15M</td>
        <td>$17M</td>
        <td>$13M</td>
        <td>$15M</td>
    </tr>
    <tr>
        <th colspan="4">Total Revenue:</th>
        <td>$293M</td>
    </tr>
</table>
```
In the first example the header "Fire" spans the first two rows and the header
"Water" spans the last three table rows. In the second example, the header
"Total Revenue" spans the first four columns of the last table row.


## Captions, Heads, Bodies, Footers
Creating more complicated tables requires more control over styling, there are
additional elements we can add to the table structure to help with this:
* <caption> adds a title to the table and can be placed right after the <table>
tag
* <thead> designates one or more rows as the header rows
* <tbody> works with <thead> and contains the body rows
* <tfoot> contains any footer rows

Here is an update of the previous revenue table with these elements:
```html
<table>
    <caption>2020 revenue projections</caption>
    <thead>
        <tr>
            <th></th>
            <th>Q1</th>
            <th>Q2</th>
            <th>Q3</th>
            <th>Q4</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th>Electronics</th>
            <td>$35M</td>
            <td>$33M</td>
            <td>$37M</td>
            <td>$40M</td>
        </tr>
        <tr>
            <th>Clothing</th>
            <td>$20M</td>
            <td>$23M</td>
            <td>$18M</td>
            <td>$27M</td>
        </tr>
        <tr>
            <th>Furniture</th>
            <td>$15M</td>
            <td>$17M</td>
            <td>$13M</td>
            <td>$15M</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th colspan="4">Total Revenue:</th>
            <td>$293M</td>
        </tr>
    </tfoot>
</table>
```


## Related
[202110210320](../202110210320) - Semantic HTML Block Elements
[202110210421](../202110210421) - Interesting Details of Inline HTML Elements
[202110210445](../202110210445) - HTML Head Elements
[202110210504](../202110210504) - HTML Media Elements

## Tags
#webdev

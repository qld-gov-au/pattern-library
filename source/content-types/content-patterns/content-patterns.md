# Content patterns

- [Figures (images, diagrams, captions)](#figures-images-diagrams-captions)
- [Data tables (sortable tables)](#data-tables-sortable-tables)
- [Downloadable document link](#downloadable-document-link)
- [Meta links](#meta-links)
- [Pull-quote](#pull-quote)
- [Pull-quote with citation](#pull-quote-with-citation)
- [Video](#video)
- [Contacts](#contacts)
- [Checklist](#checklist)
- [Side-by-side comparison](#side-by-side-comparison)
- [Side-by-side comparison (advantages and disadvantages)](#side-by-side-comparison-advantages-and-disadvantages)
- [Cross-selling links](#cross-selling-links)

Within content, patterns may be used to add semantics that can be enhanced in the presentation and behaviour layers.
- Figures (aka cut-ins)
- Breakout boxes
- Stand first

## Figures (images, diagrams, captions)
### XHTML 1.0
```html
<div class="cut-in">
  <img src="…" alt="" />
  <div class="figure-credits">…</div>
  <div class="caption">…</div>
</div>
```
### Screenshot
![Figures](images/figures.png)

Notes:
- replace class `.cut-in` with `.cut-in-alt` for alternating display. As at 13 October 2011, `.cut-in` are floated right and `.cut-in-alt` are floated left.
- use `.figure` for a figure that is not a cut in (not floated)
-use `.diagram` for diagrams to remove the styling (borders, drop shadow) reserved for photos and feature images. Combine with `.figure` for standard images and `.cut-in` for floated images.

## Data tables (sortable tables)
Use this pattern to include a data table within a content page. The template (and associated scripts) will read the information from this markup pattern and create the data table.
### Example 1
#### XHTML 1.0
```html
<table id="example1" class="data-table">
    <thead>
        <tr>
            <th>Column 1</th>
            <th>Column 2</th>
            <th>etc</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Row 1 Data 1</td>
            <td>Row 1 Data 2</td>
            <td>etc</td>
        </tr>
        <tr>
            <td>Row 2 Data 1</td>
            <td>Row 2 Data 2</td>
            <td>etc</td>
        </tr>
    </tbody>
</table>
```
#### Screenshot
![Data table 1](images/datatables-1.jpg)

### Example 2
#### XHTML 1.0
```html
<table id="example2" class="data-table">
    <thead>
        <tr>
            <th>
                <a href="birthSelect.m?sort=RegistrationNumberPart2$RegistrationNumberPart4$RegistrationNumberPart3$#matches">Reg #</a>
            </th>
            <th>
                <a href="birthSelect.m?sort=ChildGivenNames#matches">First Name</a>
            </th>
            <th>
                <a href="birthSelect.m?sort=ChildSurname$FatherSurname$MotherSurname$#matches">Last Name</a>
            </th>
            <th>
                <a href="birthSelect.m?sort=FatherGivenNames#matches">Father's Name</a>
            </th>
            <th>
                <a href="birthSelect.m?sort=MotherGivenNames#matches">Mother's Name</a>
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <a href="?id=1910/C2020">1910/C2020</a>
            </td>
            <td>Dorothy Grace</td>
            <td>Boyle</td>
            <td>Henry Courtney</td>
            <td>Teresa Maria Young</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1911/C11130">1911/C11130</a>
            </td>
            <td>James Emmet</td>
            <td>Boyle</td>
            <td>Francis</td>
            <td>Mary Ellen Murtagh</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/C38">1913/C38</a>
            </td>
            <td>Mona Marguerite</td>
            <td>Boyle</td>
            <td></td>
            <td>Emmeline Boyle</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1914/B34754">1914/B34754</a>
            </td>
            <td>Edith Caroline</td>
            <td>Boyle</td>
            <td>James Peter</td>
            <td>Jean Grant</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/C8300">1913/C8300</a>
            </td>
            <td>James Joseph</td>
            <td>Boyle</td>
            <td>John Joseph</td>
            <td>Bridget O'Brien</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1914/C8571">1914/C8571</a>
            </td>
            <td>Myrtle May</td>
            <td>Boyle</td>
            <td>Frank Patrick</td>
            <td>Ruby Margaret Duncan</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1910/C3457">1910/C3457</a>
            </td>
            <td>Eric Neils Henry</td>
            <td>Boyle</td>
            <td>Frederick Thomas</td>
            <td>Hildur Sophia Kathrina Brandt</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1912/B27845">1912/B27845</a>
            </td>
            <td>James Peter</td>
            <td>Boyle</td>
            <td>Francis</td>
            <td>Mary Cranny</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1912/B30166">1912/B30166</a>
            </td>
            <td>Naomi Ruth St.Aubyn</td>
            <td>Boyle</td>
            <td>David</td>
            <td>Caroline Beatrice Mary Hollinworth</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/B31930">1913/B31930</a>
            </td>
            <td>Ernest Frederick</td>
            <td>Boyle</td>
            <td>Frederick Thomas</td>
            <td>Hildur Sophia Catherina Brandt</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/C11557">1913/C11557</a>
            </td>
            <td>John Colin Patrick</td>
            <td>Boyle</td>
            <td>John Phelps Archibald</td>
            <td>Mary McGrath</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1912/C4458">1912/C4458</a>
            </td>
            <td>Neville Ashley</td>
            <td>Boyle</td>
            <td>Clarence Henry</td>
            <td>Bessie Fletcher Hankinson</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1914/C12591">1914/C12591</a>
            </td>
            <td>Alfred Bertram</td>
            <td>Boyle</td>
            <td>Robert Bertram</td>
            <td>Elizabeth Anna Frazer</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/C5138">1913/C5138</a>
            </td>
            <td>George Patrick</td>
            <td>Boyle</td>
            <td>Joseph Patrick</td>
            <td>Annie Amelia Soanes</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1910/C7282">1910/C7282</a>
            </td>
            <td>John Francis</td>
            <td>Boyle</td>
            <td>John</td>
            <td>Bridget O'Brien</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/C3884">1913/C3884</a>
            </td>
            <td>Stella Josephine</td>
            <td>Boyle</td>
            <td>John Francis</td>
            <td>Lily Mary Coase</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1913/C8370">1913/C8370</a>
            </td>
            <td>Alfred Charles</td>
            <td>Boyle</td>
            <td>Lurenzo Miller</td>
            <td>Rose Carline Jones</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1912/C8476">1912/C8476</a>
            </td>
            <td>Grace Ellen</td>
            <td>Boyle</td>
            <td>Francis Patrick</td>
            <td>Ruby Margaret Duncan</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1911/C7113">1911/C7113</a>
            </td>
            <td>John Henry</td>
            <td>Boyle</td>
            <td>Thomas Henry</td>
            <td>Agnes Louise Carl</td>
        </tr>
        <tr>
            <td>
                <a href="?id=1914/C11016">1914/C11016</a>
            </td>
            <td>Sydney Charles</td>
            <td>Boyle</td>
            <td>Richard Henery</td>
            <td>Dorothy Hanna Fick</td>
        </tr>
    </tbody>
</table>
```
#### Screenshot
![Data table 2](images/datatables-2.jpg)

### Example 3
#### XHTML 1.0
```html
<table id="example3" class="data-table">
    <caption>Data table 3</caption>
    <thead>
        <tr>
            <th scope="col">Column header 1</th>
            <th scope="col">Column header 2</th>
            <th scope="col">Column header 3</th>
            <th scope="col">Column header 4</th>
            <th scope="col">Column header 5</th>
            <th scope="col">Column header 6</th>
            <th scope="col">Column header 7</th>
            <th scope="col">Column header 8</th>
            <th scope="col">Column header 9</th>
            <th scope="col">Column header 10</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
        <tr>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
            <td>Table data</td>
        </tr>
    </tbody>
</table>
```
#### Screenshot
![Data table 3](images/datatables-3.jpg)

Technical requirements:
- The table must be laid out in a well-formed manner.
- The `thead` and `tbody` sections must be declared.
- The `tfoot` section is optional and will not be used to sort data.
- The table must be assigned a class name value of `data-table`.

Best practice and usage:
- Data tables are best used for tables where sorting is required or for tables with a row count exceeding twelve or more.
- Pagination is also applied if the table row-count is less than the entry count minimum of ten (10) rows. So it is best to use DataTables to large data sets.
- By default, entry count options are displayed as a dropdown menu. Search and pagination are displayed. These cannot be switched off unless specifically requested.
- Odd and even row colours are applied, and the current column used for sorting has a colour applied to aide usability. These cannot be adjusted unless specifically requested.

Notes:
- You can find useful information about how set up data tables from the usage section: https://datatables.net/usage

## Downloadable document link

The following approach allows the 'title' to be underlined without the 'meta' being underlined in all browsers.
**Use** `cite` **instead** of `span` **when the title is a citation of a publication name.**

Note: it is important to leave whitespace (a line break) between `span.title` and `span.meta`.

### XHTML 1.0-span
```html
<a href=".." class="download">
    <span class="title">Information Privacy Act 2009</span>
    <span class="meta">(PDF, 836KB)</span>
</a>
```
### Screenshot
![Download link](images/download-link.png)
### XHTML 1.0-cite
```html
<a href=".." class="download">
    <cite class="title">Information Privacy Act 2009</cite>
    <span class="meta">(PDF, 836KB)</span>
</a>
```
### Screenshot
![Download cite link](images/download-link-cite.png)

When linking to multiple formats, use a list:
### XHTML 1.0
```html
<ul>
    <li><a href=".." class="download">
        <span class="title">Subsidy application form</span>
        <span class="meta">(PDF, 220KB)</span>
    </a></li>
    <li><a href=".." class="download">
        <span class="title">Subsidy application form</span>
        <span class="meta">(RTF, 60KB)</span>
    </a></li>
</ul>
```
### Screenshot
![Download multiple format links](images/download-links.png)

## Meta links
The following approach allows the 'title' to be underlined without the 'meta' being underlined in all browsers, same as downloadable documents above.
This can be used in more generic cases which are not downloadable documents.

Note: it is important to leave whitespace (a line break) between `span.title` and `span.meta`.
### XHTML 1.0
```html
<a href=".." class="meta-link">
    <span class="title">Primary text to be underlined</span>
    <span class="meta">(comments and other meta information)</span>
</a>
```
### Screenshot
![Meta links](images/meta-link.png)

## Pull-quote
### XHTML 1.0
```html
<blockquote class="pull-quote"><p>
   Volunteers, a precious resource we can not afford to lose.
</p></blockquote>
```
### Screenshot
![Pull-quote](images/pull-quote.png)

## Pull-quote with citation
### XHTML 1.0
```html
<div class="figure">
    <blockquote class="pull-quote"><p>
   Volunteers, a precious resource we can not afford to lose.
    </p></blockquote>
    <div class="figcaption">Denise Penn </div>
</div>
```
### Screenshot
![Pull-quote with citation](images/pull-quote-cite.png)

Based on [HTML5 blockquote example](https://html.spec.whatwg.org/multipage/semantics.html#the-blockquote-element)

## Video
See [Video pattern](https://govdex.gov.au/confluence/display/SSQSWE/Video+pattern)

## Contacts
Order contact details as follows:
- Name (heading)
- Phone (franchise landing pages and above must use the 13 QGOV number; index pages and below can use more specific numbers)
- Email
- Fax (if relevant)
- Website (if relevant, do not list Queensland Government websites---the customer is already on the qld.gov.au website!)
- Postal address (follow Australia Post addressing guidelines for display)
- Address---**only if** there is a counter service available to government customers.

Use [hCard](http://microformats.org/wiki/hcard)
### XHTML 1.0
```html
<div class="vcard">
<h2 class="fn org">Aboriginal and Torres Strait Islander Partnerships</h2>
<dl>
<dt>Phone:</dt>
<dd class="tel">
<span class="type">Work</span>
13 QGOV (<span class="value">13 74 68</span>)
</dd>
<dt>Email:</dt>
<dd><a href="mailto:askatsip@communities.qld.gov.au" class="email">askatsip@communities.qld.gov.au</a></dd>
<dt>Fax:</dt>
<dd class="tel">
<span class="type">Fax</span>
<span class="value">07 3224 2070</span>
</dd>
<dt>Website:</dt>
<dd><a href="http://www.communities.qld.gov.au/atsis/" class="url">www.communities.qld.gov.au/atsis/</a></dd>
<dt>Postal address:</dt>
<dd>
<span class="adr">
<span class="type">Post</span>
<span class="post-office-box">GPO Box 806</span><br />
<span class="locality">BRISBANE</span>&nbsp;
<span class="region">QLD</span>&nbsp;
<span class="postal-code">4001</span>
</span>
</dd>
<dt>Address:</dt>
<dd>
<span class="adr">
<span class="type">Work</span>
<span class="street-extended">Level 6A, Neville Bonner Building</span><br />
<span class="street-address">75 William Street</span><br />
<span class="locality">Brisbane</span>
<abbr title="Queensland" class="region">Qld</abbr>
<span class="postal-code">4000</span>
</span>
</dd>
</dl>
</div>
```
### Screenshot
![Contacts](images/contacts.png)

## Checklist
### XHTML 1.0
```html
<ul class="checklist">
  <li>Have you entered your birth name?</li>
  <li>Have you entered your family name?</li>
  <li>Have you entered your date of birth correctly?</li>
  <li>Have you provided your email address?</li>
  <li>Have you been to infinity and beyond?</li>
  <li>Have you ticked off everything in this checklist?</li>
</ul>
```
### Screenshot
![Checklist](images/checklist.png)

### Print styles
![Checklist print style](images/checklist-print.png)

## Side-by-side comparison
### XHTML 1.0
```html
<div class="section comparison">
    …
</div>
<div class="section comparison">
    …
</div>
```
### Progressively enhanced (DHTML) to...
```html
<div><div>
    …
</div></div>
<div><div>
    …
</div></div>
```
### Screenshot
![Side-by-side comparison](images/comparison.png)

## Side-by-side comparison (advantages and disadvantages)
### XHTML 1.0
```html
<div class="section comparison advantages">
    …
</div>
<div class="section comparison disadvantages">
    …
</div>
```
### Progressively enhanced (DHTML) to...
```html
<div><div>
    …
</div></div>
<div><div>
    …
</div></div>
```
### Screenshot
![Side-by-side comparison (advantages and disadvantages)](images/comparison-advantages.png)

## Cross-selling links
### XHTML 1.0
```html
<div class="section" id="what-next"><div class="border">
    <h2>What can I read or do next?</h2>
    <ul>
        <li><a href="#">Weed control</a></li>
        <li><a href="#">Weed killer</a></li>
        <li><a href="#">Weeds</a></li>
    </ul>
</div></div>
```
### Screenshot
![Cross-selling link](images/cross-selling.png)

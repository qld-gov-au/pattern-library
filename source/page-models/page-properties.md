# Page properties

Page properties contain the last updated date and can be extended to contain attribution and creative commons licence information.
Note that page properties and metadata must match (same data, different syntax):

- last updated date must be the same as DCTERMS.modified
- creative commons licence shown must match DCTERMS.license (note US-English spelling of 'license').

```html
<dl>
    <dt class="attribution">Acknowledgments</dt>
    <dd><p>This material was sourced from BoysTown (2011). Retrieved January 30, 2012 from&mdash;Kids Helpline Hot Topic: Leaving Home.</p></dd>
 
    <dt class="visuallyhidden">Licence</dt>
    <dd id="document-licence">
        <a title="Text available under Creative Commons Attribution 3.0 Australia (CC BY 3.0) licence" rel="license" href="http://creativecommons.org/licenses/by/3.0/au/"><img alt="Creative Commons Attribution 3.0 Australia (CC BY 3.0)" src="/assets/v2/images/licences/by-80x15.png" /></a>
    </dd>
 
    <dt>Last updated:</dt>
    <dd>22 May 2012</dd>
</dl>
```


# Featured slideshow based on XML feeds

The preferred solution for publishing 'featured' content is to send an (Atom) XML feed. This approach means:

- A single source of truth for featured content in a standard format
- Featured items can be easily syndicated elsewhere (like the www.qld.gov.au homepage)
- Reduces redundant effort for franchise teams as the feed can be automatically used to populate the slideshow on the franchise landing page as well as providing an XML feed for public consumption.

## The XML feed
The source feed must be:

- In the appropriate XML format (examples available, based on Atom plus specific metadata)
- Published at **/your-franchise/assets/data/featured/source.atom**

## Dynamic content
Two content elements can be automatically populated based on the contents of the feed.

Note, in each code example:

- 'franchise name' needs to be replaced with your franchise name (e.g. 'recreation, sports and arts')
- 'franchiseslug' needs to be replaced with your franchise URL slug (e.g. 'recreation')

### Featured content slideshow
A HTML fragment file that can be included into your franchise landing page to feature the ‘high’ priority items.

Use the following in your franchise landing page:
```html
<div class="aside news-feature" id="featured">
        <div class="section-header">
            <h2>Featured</h2>
            <p class="feed"><a href="/assets/includes/dynamic/featured/feed.php?franchise=franchiseslug">
                  <img src="/assets/v2/images/skin/icon-xml-feed.png" alt="Subscribe to the franchise name featured content feed" /></a></p>
        </div>
        <!--#include virtual="/assets/includes/dynamic/featured/slideshow.php?franchise=franchiseslug"-->
    </div><!-- end #featured -->
```

### Previewing dynamic content
Pages that use these dynamic elements cannot be previewed normally from within an agency CMS (i.e. the elements that are dynamic will not render correctly in your CMS).

During initial integration, talk to the SSQ core team about establishing a time-limited preview of these pages on the SSQ infrastructure before they go-live.
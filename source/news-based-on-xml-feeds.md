# News based on XML feeds

The [product definition](https://govdex.gov.au/confluence/display/SSQSWE/Styles+and+standards) outlines page models for publishing News items to a franchise on www.qld.gov.au

The preferred solution for publishing is to send an (Atom) XML feed. This approach means:
- A single source of truth for news items in a standard format
- News items can be easily syndicated elsewhere (like the www.qld.gov.au homepage)
- Reduces redundant effort for franchise teams as the feed can be automatically used to populate the slideshow on the franchise landing page, the contents of the news archive page, and the section navigation menus on news item pages.

## The XML feed
The source feed must be:
- In the appropriate XML format (examples available, based on Atom plus specific metadata)
- Published at **/your-franchise/news/source.atom**

### Valid/expiring news items
Use a `dcterms:valid` element for each entry to specify when it should be included as a news item in franchise landing pages. Note that this will *not* affect how the feed is presented to feed readers (which will display all items), only web pages on qld.gov.au that use the atom feed as a data source.

The valid date is a range. Specify 2 W3CDTF dates separated by a / character.
#### Sample code
```html
<dcterms:valid xsi:type="dcterms:Period">2012-09-10T15:36:00+10:00/2016-01-01T00:00:00+10:00</dcterms:valid>
```
The above sample code is for a new item that is only valid from 3:36pm on 10 September 2012 until New Year (midnight on 1 January 2013).

## Dynamic content
Three content elements can be automatically populated based on the contents of the feed.

Note, in each code example:
- 'franchise name' needs to be replaced with your franchise name (e.g. 'recreation, sports and arts')
- 'franchiseslug' needs to be replaced with your franchise URL slug (e.g. 'recreation')

### News slideshow
A HTML fragment file that can be included into your franchise landing page to featured the ‘high’ priority news items.

Use the following in your franchise landing page:
```html
<div class="aside news-feature" id="news">
        <div class="section-header">
            <h2>Latest news</h2>
            <p class="feed"><a href="/assets/includes/dynamic/news/feed.php?franchise=franchiseslug">
                  <img src="/assets/v2/images/skin/icon-xml-feed.png" alt="Subscribe to the franchise name news feed" /></a></p>
            <p class="more"><a href="/franchiseslug/news/" title="View all franchise name news">View all</a></p>
        </div>
        <!--#include virtual="/assets/includes/dynamic/news/slideshow.php?franchise=franchiseslug"-->
    </div><!-- end #news -->
```

### News archive page
A page that lists all the news items in the feed, featuring the ‘high’ priority news items.

Use the following in the content area of a content page (e.g. /recreation/news/index.html ):
```html
<!--#include virtual="/assets/includes/dynamic/news/all-news.php?franchise=franchiseslug"-->
```

### News item page section navigation
A HTML fragment file containing section navigation menu that should be used on any news item pages that lists the other recent news items.

Use the following as the section nav include on each ‘news item’ page:
```html
<!--#include virtual="/assets/includes/dynamic/news/all-news-nav.php?franchise=franchiseslug"-->
```

### Previewing dynamic content
Pages that use these dynamic elements cannot be previewed normally from within an agency CMS (i.e. the elements that are dynamic will not render correctly in your CMS).

During initial integration, talk to the SSQ core team about establishing a time-limited preview of these pages on the SSQ infrastructure before they go-live.

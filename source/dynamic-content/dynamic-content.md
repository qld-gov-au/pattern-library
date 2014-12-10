# Dynamic content

## Content expiry (XSSI)

These XSSI instructions will work for Apache2, the web server on qld.gov.au
They are ignored (treated as HTML comments) in IIS.

This pattern checks the current server date against a predefined "expiry" date.
If the server date is after the expiry date, the HTML is not rendered when the page is served.

### XSSI

```html
<!--#config timefmt="%Y%m%d" -->
<!--#if expr='$DATE_LOCAL <= 20101231' -->
HTML CONTENT HERE
<!--#endif -->
```

## Time-based content

A php script is available for www.qld.gov.au hosted content to include content at certain times of the day.
This script was developed to help with displaying content outside business hours.

### SSI

```html
<!--#include virtual="/assets/includes/dynamic/time.php?virtual=INCLUDE_PATH&weekends=true&publicHolidays=true&before=HHmm&after=HHmm" -->
```

Place your content in an include file, like you normally would, then link to time.php with the location of your include and the parameters to indicate when it should be rendered.
In the above example, /housing/assets/includes/after-hours-maintenance.html is to be rendered:

    on weekends (from 12.00am Saturday through to 12.00am Monday)
    on Queensland public holidays (to be implemented)
    on other days: before 7.30am and after 5.00pm


Parameter | Description | Example
--------- | ----------- | -------
publicHolidays | Always include content on public holidays? | true | false
weekends | Always include content on weekends? |  true | false
before | include content before this time, HHmm format | 0730 (7.30am) 
after | include content on or after this time, HHmm format | 1700 (5.00pm) 
virtual | Path to your include file | /housing/assets/includes/after-hours-maintenance.html
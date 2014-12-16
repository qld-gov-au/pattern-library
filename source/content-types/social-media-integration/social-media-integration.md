# Social media integration

- [Twitter](#twitter)
- [Facebook](#facebook)

## Twitter
Please contact the QGov Online core team to have each new feed configured. The following pattern will need to be included in your pages:
```html
<div class="aside twitter-updates">
    <div class="section-header">
        <h2>Twitter feed</h2>
        <p class="more"><a href="http://twitter.com/ACCOUNT" title="More from ACCOUNT_NAME on Twitter">View all</a></p>
    </div>
 
    <!--#include virtual="/assets/includes/dynamic/twitter/aside.php?account=ACCOUNT_CODE&list=LIST_NAME&num=5"-->
</div><!-- end .aside -->
```
Notes:
* Populate **ACCOUNT** (e.g. QLDFire), **ACCOUNT_NAME** (e.g. the Queensland Fire and Rescue Service), **LIST_NAME** (e.g. es-website) and **ACCOUNT_CODE** (talk to core team to have one assigned) as relevant.
* **&list=LIST_NAME** and **&num=5** are optional.

## Facebook
Please contact the QGov Online core team to have each new feed configured. The following pattern will need to be included in your pages:
```html
<div class="aside facebook-updates">
    <div class="section-header">
        <h2>Facebook feed</h2>
        <p class="more"><a href="http://www.facebook.com/ACCOUNT" title="More from ACCOUNT_NAME on Facebook">View all</a></p>
    </div>
 
    <!--#include virtual="/assets/includes/dynamic/facebook/aside.php?account=ACCOUNT_CODE"-->
</div><!-- end .aside -->
```
Notes:
* Populate **ACCOUNT** (e.g. QLDSES), **ACCOUNT_NAME** (e.g. Queensland State Emergency Service) and **ACCOUNT_CODE** (talk to core team to have one assigned) as relevant.

TBD Display Guidelines (link to be added)
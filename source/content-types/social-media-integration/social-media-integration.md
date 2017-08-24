# Social media integration

- [Twitter](#twitter)
- [Facebook](#facebook)

## Twitter
* Remove Twitter related SSI (If any) - '<del><!-#include virtual="/assets/includes/dynamic/twitter/aside.php?account=TMFranchise&list=transport-and-motoring&num=5"-></del>'
* Add this HTML markup to a page
```html
<div class="qg-social-media">
      <div class="aside twitter-updates" data-account="TMFranchise" data-list="transport-and-motoring" data-num="5" data-widgetid="12345678899">
      	<div class="section-header"><h2>Twitter feed</h2></div>
      	<p class="more"><a href="http://twitter.com/TMFranchise/lists/transport-and-motoring" title="More from the Transport and motoring franchise on Twitter">View all</a></p>
      </div>
</div>
```
* **Configure options**
    * **data-account**="TMFranchise" - is the Twitter account name
    * **data-list**="transport-and-motoring" - is the Twitter list name
    * **data-num**="5" - is count of tweets to display
    * **data-widgetid**="12345678899" - is the Twitter widget id

## Facebook
* Remove Facebook related SSI (If any) - '<del><!-#include virtual="/assets/includes/dynamic/facebook/aside.php"-></del>'
* Add this HTML markup to a page (*if 'class="qg-social-feed"' is already there on a page then just copy 'facebook updates' block and add it inside the 'qg-social-feed' container*)
```html
<div data-role="qg-social-feed">
      <div class="aside facebook-updates" data-href="https://www.facebook.com/TMRQld">
      	<div class="section-header"><h2>Facebook feed</h2></div>
      	<p class="more">
      	<a href="http://www.facebook.com/TMRQld" title="More from The Department of Transport and Main Roads on Facebook">View all</a>
      	</p>
      </div>
</div>
```
* **Configure options**
    * **data-href**="https://www.facebook.com/TMRQld" - is the Facebook account URL


## General Social Media integration notes
* Functionality to generate Social Media widgets is located in swe_template/src/qgov/assets/v2/script/qg-social-media.js
* This is triggered via loader.js which looks for class "qg-social-media"


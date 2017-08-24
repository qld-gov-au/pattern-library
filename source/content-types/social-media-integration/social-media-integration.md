# Social media integration

- [Twitter](#twitter)
- [Facebook](#facebook)

## Twitter
##### Implementation Example:
* Remove Twitter related SSI (If any) - '<del><!-#include virtual="/assets/includes/dynamic/twitter/aside.php?account=TMFranchise&list=transport-and-motoring&num=5"-></del>'
* Append attributes to the twitter-feed HTML element
    * Container data-role should be set to **'qg-social-feed'**
    * data-account="TMFranchise" - is the twitter account name
    * data-list="transport-and-motoring" - is the twitter list name
    * data-num="5" - is count of tweets to display
    * data-widgetid="377609440007954432" - is the twitter widget id
```html
<div data-role="qg-social-feed">
      <div class="twitter-updates" data-account="TMFranchise" data-list="transport-and-motoring" data-num="5" data-widgetid="377609440007954432">
              <div class="section-header"><h2>Twitter feed</h2></div>
              <p class="more"><a href="http://twitter.com/TMFranchise/lists/transport-and-motoring" title="More from the Transport and motoring franchise on Twitter">View all</a></p>
            </div>
      </div>
</div>
```

## Facebook
* Remove Facebook related SSI (If any) - '<del><!-#include virtual="/assets/includes/dynamic/facebook/aside.php"-></del>'
* Append attributes to the twitter-feed HTML element
    * Container data-role should be set to **'qg-social-feed'**
    * data-href="https://www.facebook.com/TMRQld" - is the facebook account URL
```html
<div data-role="qg-social-feed"> <!--NOTE - if 'qg-social-feed' is already there on a page then just copy 'facebook updates' block and add it inside the 'qg-social-feed' container-->
      <div class="facebook-updates" data-href="https://www.facebook.com/TMRQld">
          <div class="section-header"><h2>Facebook feed</h2></div>
          <p class="more">
             <a href="http://www.facebook.com/TMRQld" title="More from The Department of Transport and Main Roads on Facebook">View all</a>
          </p>
     </div>
</div>
```


## General Social Media integration notes

* Functionality to generate Social Media widgets is located in swe_template/src/qgov/assets/v2/script/qg-social-media.js
* This is triggered via loader.js which looks for class name → class="qg-social-media"
* Please make sure to include only one container data-role 'qg-social-feed' on a page.


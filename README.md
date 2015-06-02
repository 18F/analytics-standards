This project memorializes the standards that 18F sets for itself for implementing various forms of analytics, namely website analytics but also api analytics.  Every project that has a digital presence will integrate appropriate analytics to better learn what our users need and want.  This follows well-established best practices and equips the team to better deliver great product.

Furthermore, we feel that access to analytics data should be widely available to teammates, partners, and the public.  There are countless use cases where a fellow 18F-er might benefit from easy access to a project's website analytics and very few reasons to limit that access.  Along the same lines, we believe that we are better able to serve our agency partners when they have ready access to robust analytics for their project.


## 18F Team Standards for Website Analytics

Webpages should integrate both the 18F Google Analytics (GA) as well as the Digital Analytics Program (DAP).  Web services should integrate the `api.data.gov` service.

Every 18F team member should be given read/collaborate access to the 18F Gs account in the first two weeks on the job.  At the same time, they should be informed of the process for gaining access to the DAP and GSA's GA account.

Once analytics has been set up, it's recommended to share read/collaborate access with the agency partners that are working on a project with you.  Even if they do not express interest, it's better to enable them so that there's no excuse for the conversation.

## 18F Snippet Standards for Website Analytics

### 18F Account Snippet

The purpose of the 18F tracker snippet is to simplify/centralize analytics tracking and provide everyone within the organization access to all 18F projects' data. Additionally the snippet contains a few modifications to meet specific privacy and security standards.
Customizations
* [Anonymize IP](https://developers.google.com/analytics/devguides/collection/analyticsjs/field-reference#anonymizeIp)
* [Force SSL](https://developers.google.com/analytics/devguides/collection/analyticsjs/field-reference#forceSSL)

#### UA Code
Message us on [g-analytics slack channel](https://18f.slack.com/messages/g-analytics/) and the Analytics Guild will give you a UA code linked to an account, which all 18F members can access.


#### JavaScript Code Snippet
```javascript
(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

ga('create', '<<UA-CODE>>', 'auto');
ga('set', 'anonymizeIp', true);
ga('send', 'pageview');
```

## Digital Analytics Program Snippet
For more information about DAP visit thier [site](https://www.digitalgov.gov/services/dap/). Snippet information taken from [DAP Github page](https://github.com/digital-analytics-program/gov-wide-code).

#### Digital Analytics Program government-wide code
Provides a JavaScript file for US federal agencies to link or embed in their websites to participate in the Digital Analytics Program.

The most current version of DAP GA code is:

* [`Universal-Federated-Analytics.js`](Universal-Federated-Analytics.js) (full)
* [`Universal-Federated-Analytics-Min.js`](Universal-Federated-Analytics-Min.js) (minified)

#### Central hosting

The central URLs for the Digital Analytics Program JS snippet are:

* `https://dap.digitalgov.gov/Universal-Federated-Analytics.js` (full)
* `https://dap.digitalgov.gov/Universal-Federated-Analytics-Min.js` (minified)

Agencies are encouraged to use the following HTML snippet to participate in the Digital Analytics Program:

```html
<!-- We participate in the US government's analytics program. See the data at analytics.usa.gov. -->
<script id="_fed_an_ua_tag" src="https://dap.digitalgov.gov/Universal-Federated-Analytics-Min.js"></script>
```

## api.data.gov

Each project that builds an API should ensure that it is tracking how the API is being used.  The easiest means for 18F to do this is by integrating its own [api.data.gov service](https://api.data.gov/).

This ensures that system owners and stakeholders can monitor how the web service is being used, but it also provides further functionality.  Api.data.gov also provides the ability to offer API keys, set different rate limits, and to block abusive users.

To learn more, email `api.data.gov@gsa.gov`.

## Processes

_Hyperlink these bullet points to directions_

* How to add the 18F GA to a project
* How to gain access to the 18F GA data
* How to add the DAP GA to a project
* How to gain access to the DAP GA project
* Add api.data.gov to an API
* Administer my api.data.gov integration
* Share access to the api.data.gov data.

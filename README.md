This project memorializes the standards that 18F sets for itself for implementing various forms of analytics— namely website  but also API. Every project that has a digital presence will integrate appropriate analytics to better learn what our users need and want. This follows well-established best practices and equips the team to better deliver great product.

Access to analytics data should be widely available to teammates, partners, and the public. There are countless use cases where a fellow 18F team member can benefit from easy access to a project's website analytics and very few reasons to limit that access. We are better able to serve our agency partners when they have ready access to robust analytics for their project.

## 18F team standards for analytics

Webpages should integrate both the 18F Google Analytics (GA) as well as the Digital Analytics Program (DAP).

Every 18F team member should be given read/collaborate access to the 18F GA account in the first two weeks on the job.  At the same time, they should be informed of the process for gaining access to the DAP and GSA's GA account.

Once analytics has been set up, it's recommended to share read/collaborate access with the agency partners working on a project with you.  Even if they do not express interest, it's better to enable them so there's no excuse for the conversation.

Separately, 18F projects that build APIs should integrate the `api.data.gov` service to track how developers use their web service.

## 18F snippet standards for website analytics

### 18F account snippet

The purpose of the 18F tracker snippet is to simplify/centralize analytics tracking and provide everyone within the organization access to all 18F projects' data. Additionally, the snippet contains a few modifications to meet specific privacy and security standards.

**Customizations**

* [Anonymize IP](https://developers.google.com/analytics/devguides/collection/analyticsjs/field-reference#anonymizeIp)
* [Force SSL](https://developers.google.com/analytics/devguides/collection/analyticsjs/field-reference#forceSSL)
* Upgrade the [protocol-relative URL](http://www.paulirish.com/2010/the-protocol-relative-url/) to an HTTPS URL when making the initial connection to `www.google-analytics.com`.

#### UA code

Message us on the [#g-analytics slack channel](https://18f.slack.com/messages/g-analytics/), and the Analytics Guild will give you a UA code linked to an account, which all 18F members can access.


#### JavaScript code snippet

To add the 18F snippet:

* Copy the code below
* Replace the `<<UA-CODE>>` with the ua-code that you got from the Analytics Guild
* Place it immediately before the closing `</head>` tag

```javascript
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', '<<UA-CODE>>', 'auto');
  ga('set', 'anonymizeIp', true);
  ga('set', 'forceSSL', true);
  ga('send', 'pageview');
</script>
```

### Digital Analytics Program snippet

For more information about DAP, visit their [site](https://www.digitalgov.gov/services/dap/) and their [GitHub repository](https://github.com/digital-analytics-program/gov-wide-code).

The Digital Analytics Program provides [secure, central hosting](https://www.digitalgov.gov/2015/08/14/secure-central-hosting-for-the-digital-analytics-program/) for its JavaScript snippet. 

Place the following tag **at the bottom of your HTML**:

```html
<script src="https://dap.digitalgov.gov/Universal-Federated-Analytics-Min.js"
id="_fed_an_ua_tag"></script>
```

**Note:** The above `<script>` tag is **loaded synchronously**, so you should put it at the bottom of your HTML. DAP has an [outstanding bug affecting asynchronous usage](https://github.com/digital-analytics-program/gov-wide-code/pull/28). This bug should be fixed in a future version of the DAP -- in which case, at that time you may want to update your tag again to add the `async` attribute.


## 18F team standards for API analytics

Where website analytics measures visitor traffic on a website, API analytics [measure how developers use a web service](https://pages.18f.gov/API-All-the-X/pages/api_analytics/).  18F manages a light but powerful tool to accomplish this task: [api.data.gov](https://api.data.gov/).

Each 18F project that builds an API should ensure it's tracking how the API is being used.  The easiest means to do this is by [integrating the api.data.gov service](http://api.data.gov/about/#how-to-participate).

This ensures that system owners and stakeholders can monitor how the web service is being used. It also provides further functionality.  Api.data.gov additionally provides the ability to offer API keys, set different rate limits, and to block abusive users.  By integrating api.data.gov, the project not only gains its direct benefits but also gains the benefits of 18F further dogfooding its own work.

To learn how to integrate api.data.gov into your project's API, ask in the #wg-api channel in Slack or email `api.data.gov@gsa.gov`.  Integration is fast and easy, but, for everyone's convenience, it's better to begin this conversation during the planning and pre-production stages.

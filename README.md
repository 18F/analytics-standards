This project memorializes the standards that 18F sets for itself for implementing various forms of analytics, namely website analytics but also api analytics. Every project that has a digital presence will integrate appropriate analytics to better learn what our users need and want. This follows well-established best practices and equips the team to better deliver great product.

Access to analytics data should be widely available to teammates, partners, and the public. There are countless use cases where a fellow 18F-er can benefit from easy access to a project's website analytics and very few reasons to limit that access. We are better able to serve our agency partners when they have ready access to robust analytics for their project.

## 18F Team Standards for Analytics

Webpages should integrate both the 18F Google Analytics (GA) as well as the Digital Analytics Program (DAP).

Every 18F team member should be given read/collaborate access to the 18F GA account in the first two weeks on the job.  At the same time, they should be informed of the process for gaining access to the DAP and GSA's GA account.

Once analytics has been set up, it's recommended to share read/collaborate access with the agency partners that are working on a project with you.  Even if they do not express interest, it's better to enable them so that there's no excuse for the conversation.

Separately, 18F projects that build APIs should integrate the `api.data.gov` service in order to track how developers use their web service.

## 18F Snippet Standards for Website Analytics

### 18F Account Snippet

The purpose of the 18F tracker snippet is to simplify/centralize analytics tracking and provide everyone within the organization access to all 18F projects' data. Additionally the snippet contains a few modifications to meet specific privacy and security standards.

**Customizations**

* [Anonymize IP](https://developers.google.com/analytics/devguides/collection/analyticsjs/field-reference#anonymizeIp)
* [Force SSL](https://developers.google.com/analytics/devguides/collection/analyticsjs/field-reference#forceSSL)
* Upgrades the [protocol-relative URL](http://www.paulirish.com/2010/the-protocol-relative-url/) to an HTTPS URL when making the initial connection to `www.google-analytics.com`.

#### UA Code

Message us on the [#g-analytics slack channel](https://18f.slack.com/messages/g-analytics/) and the Analytics Guild will give you a UA code linked to an account, which all 18F members can access.


#### JavaScript Code Snippet

To add the 18f snippet...

* copy the code below
* replace the `<<UA-CODE>>` with the ua-code that you got from the Analytics Guild
* add to the bottom of page before the `</body>`

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

### Digital Analytics Program Snippet

For more information about DAP, visit their [site](https://www.digitalgov.gov/services/dap/) and their [GitHub repository](https://github.com/digital-analytics-program/gov-wide-code).

#### Digital Analytics Program government-wide code

Provides a JavaScript file for US federal agencies to link or embed in their websites to participate in the Digital Analytics Program.

The most current version of DAP GA code is:

* [`Universal-Federated-Analytics.js`](https://raw.githubusercontent.com/digital-analytics-program/gov-wide-code/master/Universal-Federated-Analytics.js) (full)
* [`Universal-Federated-Analytics-Min.js`](https://raw.githubusercontent.com/digital-analytics-program/gov-wide-code/master/Universal-Federated-Analytics-Min.js) (minified)

**Do not hot-link to the above files.** Download and self-host them in your application.

## 18F Team Standards for API Analytics

Where website analytics measures visitor traffic on a website, API analytics [measures how developers use a web service](https://pages.18f.gov/API-All-the-X/pages/api_analytics/).  18F manages a light but powerful tool to accomplish this task, [api.data.gov](https://api.data.gov/).

Each 18F project that builds an API should ensure that it is tracking how the API is being used.  The easiest means for 18F to do this is by [integrating the api.data.gov service](http://api.data.gov/about/#how-to-participate).

This ensures that system owners and stakeholders can monitor how the web service is being used, but it also provides further functionality.  Api.data.gov also provides the ability to offer API keys, set different rate limits, and to block abusive users.  By integrating api.data.gov, the project not only gains its direct benefits but also gains the benefits of 18F further dogfooding it's own work.

To learn how to integrate api.data.gov into your project's API, ask in the #api channel in Slack or email `api.data.gov@gsa.gov`.  Integration is fast and easy, but it is better to begin this conversation during the planning and pre-production stages for everyone's convenience.

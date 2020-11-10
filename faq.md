### What is the difference between 18F Google Analytics and the Digital Analytics Program (DAP)?

The [Digital Analytics Program](http://www.digitalgov.gov/services/dap/) and 18F Google Analytics are different services with two distinct code snippets. 18F projects should participate in both services.

##### Digital Analytics Program
The [Digital Analytics Program](http://www.digitalgov.gov/services/dap/) is a shared service available to all federal agencies to provides website analytics. DAP both offers a fully functional analytics service to agencies but also integrates with a cross-government combined analytics dashboard.  Staff at participating agencies are able to access the full, government-wide data.

Furthermore, the Digital Analytics Program offers government agencies services such as guidance, training, and web analytics tools.  Government sites including 18F sites can be added to the DAP Google Analytics account via a code snippet.

##### 18F Google Analytics
18F Google Analytics is an account only for 18F websites. Since 18F is the owner of the account it allows us to make special modifications not avaiable through the DAP. To add a new 18F site to our Google Anaytics account follow the [18F Snippet Standards for Website Analytics directions](https://github.com/18F/analytics-standards#18f-snippet-standards-for-website-analytics).


### How do I get access to the 18F Google Analytics?  

18F team members should receive an invitation to the 18F GA account and do not need to do anything to ensure this.  However, if you would like it more quickly, post in the #analytics channel on Slack and an admin will add you directly.  

### How do I get access to the government-wide DAP data?  

Email [dap@support.digitalgov.gov](mailto:dap@support.digitalgov.gov) and say that you would like access to the DAP.  They will send back [this form](https://docs.google.com/forms/d/1BVcvBge74kaWpSkIaQ1x1sfAE3aa0YMnVe3kXuD8z9k/viewform) for you to fill out. [For the question `Website(s) most interested in/aligned with`, simply put `18f.gsa.gov`.]  

If you want to speed things up, you can fill out the form first, and tell them that you have done so when you email.  Once the DAP team has given you access, you will see a new link to `Government-Wide Account` when you log into [Google Analytics](https://www.google.com/analytics) with your work email.  

### Can I give access to a project's analytics to a client?

Yes, please!  Not only can you, but you should!

### How do I give access to a project's analytics to a client?

 In order to grant them access, we need to know what email address they want to use. If it is not a gmail (or google apps) email address, then they need to first go to google.com/analytics and create an account there using their preferred email address ([alternate link](https://accounts.google.com/SignUpWithoutGmail)).

Then post in `#g-analytics` on Slack the email addresses of the client staff who you want to give access.  If you're not the project lead, make sure they are aware by cc'ing them in the slack post.

They will be given `Collaborate` and `Read & Analyze` permissions specific only to their project and will receive an email notification.

It is incumbent on the project team to track when analytics access should be removed. If a partner moves on and should no longer have access, the 18F team needs to contact #g-analytics on Slack and specify that access should be rescinded.

_Note that we are not currently in a position to grant access to Digital Analytics Program data to 3rd parties._


### We've completed a project and are transitioning it to the client to own from here on.  How do we hand off access and management of the 18F Google Anallytics to them?  

Interestingly, there's no way to transfer a Google Analytics property from one account to another.  The client could remove the UA code associated with the 18F account and replace it with their own, but they would lose all historical data.  Instead of that, we should ask the client who on their team we should grant the 'Manage Users' permission for and request this change in the #g-analytics channel in Slack.  This will allow the client team to manage user access to their property for the indefinite future.  

They may also want to think about adding a UA code from their own agency's Google Analytics account to begin collecting data and to allow them the complete functionality that is available to account owners, however we should advise them to keep in place the 18F account UA-code for the indefinite future alongside it.  

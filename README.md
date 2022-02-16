# git-automated-protectedbranches
Please create a simple web service that listens for organization events to know when a repository has been created. When the repository is created please automate the protection of the main branch. Notify yourself with an @mention in an issue within the repository that outlines the protections that were added.

## Pre-requisite
- Python (In this example python3 is used)
- Flask
- ngrok
- All the dependencies mentioned in requirements.txt

## Steps to run webservice
- Install all the pre-requisites. ***`Instructions ?`***
- Set GitHub token (GH_TOKEN). Extract your personal token from GitHub and add it as your environment variable. Use the following command to add it as an environment variable :
**export GH_TOKEN = (your personal token)**
- Set your username in app.py ***`Hardcoding`***
- Start the local web service using 'flask run --host=0.0.0.0 &'
- Start the forwarding service using 'ngrok http https://localhost:5000'. You can use the exact URL too.
- Note the forwarding address from ngrok (in this case hhttp://b99e-2607-fea8-4e0-2f00-e9ef-e0aa-ad26-bfed.ngrok.io)

![](../../../Desktop/Screen Shot 2022-01-30 at 1.19.43 PM.png)![] ***`Broken link`***
- (../../../Desktop/Screen Shot 2022-01-30 at 1.19.19 PM.png) ***`Broken link`***
- 
- Add webhook to GitHub organization and add the payload URL. ***`Instructions ?`***
- Payload URL = Forwarding address from ngrok
- Select Content type as application/json
- Select 'Repositories' and events to trigger.
- Save the webhook.

# Test
- Create a new repo
- Check if the branch is auto protected and you are notified about the issue.

**Bugs and issues -**
-ngrok forwarding URL isn't working.

**References**
https://ngrok.com/docs
https://docs.github.com/en/developers/webhooks-and-events/webhooks/about-webhooks
https://github.com/jimzucker/github-webhooks
https://github.com/zkoppert/Auto-branch-protect
https://docs.github.com/en/rest


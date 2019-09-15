# Slack Spring Boot Starter Heroku

<a href="https://twitter.com/kreait"><img src="https://img.shields.io/badge/Follow-kreait-brightgreen.svg?style=flat&logo=twitter"></a>
<a href="https://www.instagram.com/kreait/"><img src="https://img.shields.io/badge/Follow-kreait-brightgreen.svg?style=flat&logo=instagram"></a>
<a href="https://discord.gg/fXfQmdJ"><img src="https://img.shields.io/badge/chat-discord-brightgreen.svg?logo=discord&style=flat"></a>

## Quickstart
### Preparation

#### 1. Create a new Slack App
Head over to https://api.slack.com/apps and create your new Slack App.

#### 2. Set up your Slack App

There is no right order to do this. If you know what your future Heroku instance will be named, you can progress this guide step-by-step.
Let's assume your Heroku instance will hold the name ```slackboot```.

1. Enable Incoming Webhooks

2. Enable Interactive Components<br>
The Request-URL will be
```https://slackboot.herokuapp.com/interactive-components```

3. Adding Slash Commands:<br>
Create a new Slash Command with these parameters:
    - Command: ```/rock-paper-scissors```
    - Request URL: ```https://slackboot.herokuapp.com/commands```
    - Short Description: ```Play Rock Paper Scissors```
    - Usage Hint: ```optional```
    
4. Adding a Bot User:<br>
You can chose whatever you like for the Display name and default name.

5. OAuth & Permissions - adding a Redirect URL & Managing Scopes:<br>

    This step is important since you have to install the App in order to get a Team-ID that is needed to use the Slack App (for authentication purposes).
    In our case, since we chose ```slackboot``` as a name, our Redirect URL will be ```https://slackboot.herokuapp.com/installation```.

    In the same menu, add the following Permission Scopes:
    - chat:write:bot
    - incoming-webhook

Now hit ```Install App to Workspace```
and you will get the following (sensitive) information about your Slack App:

    - The OAuth Token
    - The Client-ID
    - The Client-Secret
    - The Signing-Secret

Since you will be prompted to enter these while deploying on Heroku.
Additionally you’ll need to have the following settings in your Slack-App Configuration:

- Event Subscriptions: channel.message
- Slash Commands: /rock-paper-scissors with {ngrok_host}/commands
- OAuth Scope: channels:read and channels:write

### Deploy to Heroku

After the preparations are made, you can deploy your App on Heroku.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

After deploying, go to https://api.slack.com/apps - select your app - go to Manage Distribution and hit ```Add to Slack``` to finalize your installation.

## Support

Feel free to join our [Discord](https://discord.gg/fXfQmdJ) - We are happy to help!
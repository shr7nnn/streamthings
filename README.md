# StreamThings

StreamThings is a Stream Deck plugin for controlling Samsung SmartThings scenes, lights, switches, and supported devices.
- Inspired by https://github.com/thibautsabot/streamdeck-plugin-smartthings
- The plugin is designed around OAuth which is permanent, not like PAT which is 24-hour personal access tokens

# Instructions

## 1. Install the SmartThings CLI
You will need this to create:
- a `Client ID`
- a `Client Secret`
  
Installation
> Homebrew (MacOS)
  brew install smartthingscommunity/smartthings/smartthings
> Windows
  Download and run the smartthings.msi installer from the latest Release.
  https://github.com/SmartThingsCommunity/smartthings-cli

## Run in Terminal/Command Prompt:
```bash
smartthings login
```

## Create an app:
```bash
smartthings apps:create
```

## When prompted, use:
- App type: `OAuth-In App`
- Name: `StreamThings`
- Description: `Stream Deck SmartThings control`
- Target URL: leave blank if allowed
- Redirect URI: `https://shr7nnn.github.io/callbackstreamdeck/`

## Select these scopes:
- `r:devices:*`
- `x:devices:*`
- `r:scenes:*`
- `x:scenes:*`

## Copy the generated `clientId` and `clientSecret`


## Install the Plugin & Configure
1. Add any StreamThings action to a key
2. In the property inspector, enter:
- `Client ID`
- `Client Secret`

3. Click `Sign In | Get Code`
4. Your browser will open SmartThings sign-in
5. Approve access
6. After redirect, copy the returned code from the page
7. Paste that code into `Returned Code`
8. Click `Connect`

When connection succeeds:
- the status indicator turns green
- the plugin stores the OAuth tokens locally
- access tokens refresh automatically when needed

## Made with love by shr7n.

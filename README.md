# StreamThings

StreamThings is a Stream Deck plugin for controlling Samsung SmartThings scenes, lights, switches, and supported devices.

- Inspired by [thibautsabot/streamdeck-plugin-smartthings](https://github.com/thibautsabot/streamdeck-plugin-smartthings)
- The plugin is designed around OAuth, which is permanent, unlike PAT which uses 24-hour personal access tokens

## Instructions

### 1. Install the SmartThings CLI

You will need this to create:
- a `Client ID`
- a `Client Secret`

#### Installation

**Homebrew (macOS)**

```bash
brew install smartthingscommunity/smartthings/smartthings
```

**Windows**

Download and run the `smartthings.msi` installer from the latest release:

[https://github.com/SmartThingsCommunity/smartthings-cli](https://github.com/SmartThingsCommunity/smartthings-cli)

### 2. Run in Terminal or Command Prompt

```bash
smartthings login
```

### 3. Create an App

```bash
smartthings apps:create
```

### 4. When Prompted, Use

- App type: `OAuth-In App`
- Name: `StreamThings`
- Description: `Stream Deck SmartThings control`
- Target URL: leave blank if allowed
- Redirect URI: `https://shr7nnn.github.io/callbackstreamdeck/`

### 5. Select These Scopes

- `r:devices:*`
- `x:devices:*`
- `r:scenes:*`
- `x:scenes:*`

### 6. Copy the Generated Credentials

Copy the generated:
- `clientId`
- `clientSecret`

## Install the Plugin and Configure

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

## Made with love by shr7n <3

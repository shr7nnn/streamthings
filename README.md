# StreamThings

StreamThings is a Stream Deck plugin for controlling SmartThings scenes, lights, switches, and supported devices.

Plugin package:
- `dist/StreamThings.streamDeckPlugin`

## What It Does

StreamThings adds these actions to Stream Deck:
- `Scene`
- `Device`
- `Light`
- `Switch`

You can use it to:
- run SmartThings scenes
- toggle switches
- control supported lights
- assign SmartThings devices directly to Stream Deck keys

## Install

1. Open `dist/StreamThings.streamDeckPlugin`
2. Confirm installation in Stream Deck
3. Drag a `Scene`, `Device`, `Light`, or `Switch` action onto a key

## Before You Connect

Each user needs their own SmartThings OAuth app credentials.

You will need:
- a `Client ID`
- a `Client Secret`
- a redirect URL

This plugin uses this redirect URL by default:

`https://shr7nnn.github.io/callbackstreamdeck/`

## Create Your SmartThings App

SmartThings currently provides the simplest app creation flow through the SmartThings CLI.

1. Install the SmartThings CLI
2. Sign in:

```bash
smartthings login
```

3. Create an app:

```bash
smartthings apps:create
```

4. When prompted, use:
- App type: `OAuth-In App`
- Name: `StreamThings`
- Description: `Stream Deck SmartThings control`
- Target URL: leave blank if allowed
- Redirect URI: `https://shr7nnn.github.io/callbackstreamdeck/`

5. Select these scopes:
- `r:devices:*`
- `x:devices:*`
- `r:scenes:*`
- `x:scenes:*`

6. Save the generated `clientId` and `clientSecret`

Important:
- keep your `clientSecret` private
- each user should create their own SmartThings app

## Connect The Plugin

1. Add any StreamThings action to a key
2. In the property inspector, enter:
- `Client ID`
- `Client Secret`

3. Click `Sign In | Get Code`
4. Your browser will open SmartThings sign-in
5. Approve access
6. After redirect, copy the returned code from the callback page
7. Paste that code into `Returned Code`
8. Click `Connect`

When connection succeeds:
- the status indicator turns green
- the plugin stores the OAuth tokens locally
- access tokens refresh automatically when needed

## Use The Actions

## Scene

1. Drag `Scene` onto a key
2. Open the action settings
3. Pick the scene you want
4. Press the key to run that scene

## Device

1. Drag `Device` onto a key
2. Pick the device
3. Choose the behavior if shown
4. Press the key to control it

## Light

1. Drag `Light` onto a key
2. Pick the light
3. Press the key to toggle it

## Switch

1. Drag `Switch` onto a key
2. Pick the switch
3. Press the key to toggle it

## Notes

- The plugin is designed around OAuth, not 24-hour personal access tokens
- Tokens are stored on the local machine running Stream Deck
- If you change your SmartThings app credentials, reconnect the plugin
- If device or scene lists do not appear, reconnect and check your scopes

## Build From Source

```bash
npm install
npm run build
npm run package
```

The packaged plugin will be written to:

`dist/StreamThings.streamDeckPlugin`

Made by shr7n.

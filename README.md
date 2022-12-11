# Discord Console hacks
[![License: GPL v3+](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

:warning: **Note:** I'm not affilated with Discord and do not encourage using any of these scripts. Use everything here at your own risk. This is meant for **educational purposes only** and using these codeblocks may result in your account being disabled/terminated.

## Community

<details>
  <summary>We're switching to Matrix!</summary>
  
Matrix is a community-based, decentralized, privacy friendly, end-to-end encrypted (super secure), uncensorable and open source messaging protocol, which unlike discord promotes custom clients and modifications. There are multiple different clients available, the most popular one (and also the refrence implementation) is Element. It runs on most OSes and also has a pretty good web version. For more information check out https://matrix.org and https://element.io.<br>
I often get asked: "*If Matrix is so super awesome, why didn't you start using earlier?*"<br>
Well actually I've been using Matrix for quite a long time now. I never really thought about using it for this Discord stuff.
</details>

Here's the invite to the community: https://matrix.to/#/#discord-oxygen:matrix.org

The main community is on matrix, most channels are encrypted and can only be accessed from within matrix.
For those of you who can't use Matrix we created the Discord Server, its bridged to the community (=every message you send in Discord automatically appears in matrix and vice-versa)<br>
Here's the invite link: https://discord.gg/m8jbrkzExz (4th server)<br>


Please don't use console hacks not sent by me, or you might risk losing your account.<br>
I'll update this invite regularly, if e.g. my account gets compromised or Discord shuts down the server, I will create a new account, a new server and then will update the invite above.<br>
If the invite doesn't work anymore, it means the server got deleted and you need to wait until I can create a new account.

## Inner workings of Discord

**Disclaimer:** The Information provided in this section is obtained through reverse-engineering and NOT verfied for it's accuracy. Therefore it might be outdated aswell.
<details>
  <summary>Expand</summary>

### Discord Token Syntax

<details>
<table>
  <tr><th></th><th>Example</th></tr>
  <tr><td>User ID Encoded in Base64</td><td>NTzQvPcLBacBmgajXQc7QAaU</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>Timestamp -epoch(1293840000) converted to base64</td><td>XCgboz</td></tr>
  <tr><td>Dot</td><td>.</td></tr>
  <tr><td>HMAC consiting of 27 chars (uppercase/lowercase letters, numbers, - or _)</td><td>c4t51kFWSEmdmaPnKoyUuu8E78E</td></tr>
</table>
There is this awesome diagram from <a href="https://github.com/hxr404/Discord-Console-hacks/issues/2">#2</a> wich shows the exact token structure:<br><br>
<img src="https://user-images.githubusercontent.com/34555296/120932740-4ca47480-c6f7-11eb-9270-6fb3fbbd856c.png"></img> <br>
</details>
<br>

### Discords Internal Server Structure

<details>
Check out this article about Reverse Engineering Discord, and the proof that Discord decrypts your encrypted data: <a href="https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626">https://medium.com/tenable-techblog/lets-reverse-engineer-discord-1976773f4626</a><br>
They can also read your messages (e.g. in DM's), log all edits and deleted messages and record your voice calls.

![grafik](https://user-images.githubusercontent.com/55095883/116671170-e9f5e580-a9a0-11eb-98f9-3bcd65b9fdbf.png)

<br>
<sup>How sending Audio/Video Messages in Discord Works.</sup>
</details>
<br>
</details>

## Console Hacks

As stated in my disclaimer, I don't promote using any kind of client modifications. Please don't use the code found here for illegal / hacking purposes, or you might risk seeing this error message:<br>

![image](https://user-images.githubusercontent.com/55095883/134189043-4da003de-4829-4d60-888a-6014ebb5c2b8.png)

<details>
  <summary>Expand</summary>

## How to use these Hacks

It only works on Web and Desktop Versions (Windows, Linux, MacOS), not on Mobile.
1. Press CTRL + SHIFT + I to toggle Developer Tools (Discord is based on electronjs wich is basically google chrome)
2. Click on "Console" if not already selected
3. Paste the script in
4. Press enter

### Obtaining your Token

Copies your Token into the clipboard.<br>
**:warning: DO NOT GIVE THIS TO ANYONE. It grants full access to your account.**
<details>
<summary>Expand</summary>

Paste this into the Console (while being logged in)

```js
window.webpackChunkdiscord_app.push([[Math.random()], {}, (req) => {for (const m of Object.keys(req.c).map((x) => req.c[x].exports).filter((x) => x)) {if (m.default && m.default.getToken !== undefined) {return copy(m.default.getToken())}if (m.getToken !== undefined) {return copy(m.getToken())}}}]); console.log("%cWorked!", "font-size: 50px"); console.log(`%cYou now have your token in the clipboard!`, "font-size: 16px")
```

The token should be in your clipboard now.
</details>
<br>

### Logging in using Token

Modifies the login screen so you can use tokens to log in.

<details>
<summary>Expand</summary>

Paste this into the Console (CTRL + SHIFT + I) on the login screen (you need to be logged out)

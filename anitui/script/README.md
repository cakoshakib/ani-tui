This is a fork of [vlc-ani-discord](https://github.com/cakoshakib/vlc-ani-discord) made specifically for ani-tui

## vlc-ani-discord

vlc-ani-discord is a tool made for Anime watchers using VLC. Integrates VLC Media Player with Discord to display rich presence status text. Automatically updates user's AniList episode count when playback has completed using AniList's GraphQL API.

## Showcase 

![GIF of Discord Rich Presence](https://i.imgur.com/wJJOEHG.gif)

Icon cycles between random anime characters

## Prerequisites 
- VLC Media Player
- Node/NPM
- Discord
- AniList account

## Setup

### Initial Setup 
- Run `npm install`
- Rename `.env_template` to `.env`

### AniList
- Input your AniList username into `ANILIST_USERNAME` in the `.env`
- Create an [API Client](https://anilist.co/settings/developer)
- Input the client id, redirect url, and client secret into the `.env` file
- Run `node ./src/api/auth/auth_url.js`
- Approve authentication and then copy token provided at the end of the redirected URL into `ANILIST_AUTHTOKEN` in the `.env`
- Run `node ./src/api/auth/gen_token.js` and copy JWT token generated into `ANILIST_JWT` in the `.env`

### VLC
- Open VLC and go to `Tools > Preferences`
- Click `All` under `Show Settings` and search `Main Interfaces`
- Enable `Web` and set password under `Main Interfaces > Lua > Lua HTTP`
- Visit `localhost:8080` to ensure a web interface is visible
- Input password into `VLC_PW` of the `.env` file

### Running the Program
- Open an Anime episode and run `npm start`!

## Notes
- If you would like to use the AniList episode updating feature, the anime must already be in your "Watching" list on AniList.
- The parser may fail in retrieving the episode number and/or title if it is inordinary, please submit an issue if this occurs.
- If you would like to change the icon/name displayed on Discord Rich Presence, create your own Application in the [Discord Developer portal](https://discord.com/developers/applications) and change the Client ID in the `.env` file. Then simply edit `./src/utils/icon.js` with the name(s) of your uploaded art assets.

---
## Disclaimer 
This project is unofficial and has no affiliation with VLC, AniList, or Discord.

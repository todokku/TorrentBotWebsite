# What is this repo?
This is a repo to create a website that uses aria2 to mirror files from the internet or torrents into Google Drive. This can be deployed onto a personal server using Docker or on Heroku.

## Features supported:
- Mirroring direct download links to Google Drive
- Mirroring torrent magnet links to Google Drive
- Mirroring downloads into a Team Drive
- Download/upload speeds and ETAs

## Disclaimer
- You will need to deploy this bot either on your own server using Docker or on Heroku using a free Heroku account
- Credit for all code goes to https://github.com/maple3142/heroku-aria2c

# Tutorial
## Rclone.conf setup
- Setup Rclone by following these instructions: https://rclone.org/docs/
- After you're done with the setup 'rclone.conf' will be created in C:\Users\USERNAME\.config\rclone
- Open 'rclone.conf' there should be text inside looking like this
```conf
[Drive Name]
type = drive
client_id = 1234567890qwertyuiopasdfghj.apps.googleusercontent.com
client_secret = qwert_yuiopasdfghjlzxcvb
scope = drive
token = {"access_token":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx","token_type":"Bearer","refresh_token":"1//xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx","expiry":"2020-02-0123:01:01.12345678+01:00"}
team_drive = 12A_345rSFJDIWD
others entries...
```
- Copy from `type = ...` to  `... token = ...` or `team_drive = ...` if you used a Team Drive in the Rclone setup
- From the above copied items change each line break to `\n`
- Save this text somewhere
## Deploying
- Click the 'Deploy to Heroku' button below
- In `ARIA2C_SECRET` put any text (make sure to save the text for later)
- In `HEROKU_APP_NAME` put the name of your Heroku app, it will be above on the same page
- In `RCLONE_CONFIG` paste the saved text you made from the 'Rclone.conf setup' part of this tutorial
- In `RCLONE_DESTINATION` set a path you want to store your downloaded files. It should have a `/` before it. So it should look something like this: `/NameOfFolder`

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)
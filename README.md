# BAC Tracker
A tracker for Blaze and Caves Minecraft advancement pack. The tracker manages and puts all advancements in a google spreadsheet.
This branch of the tracker offers FTP support for multiplayer servers on external hosts.
It modifies the original code to download the necessary files from the server via FTP and creates a mock `world` folder within the tracker directory to read from.
I developped this on macOS so I can't offer exe support like the normal tracker.

This branch does *not* support SFTP. For SFTP support check out Pikachu's branch [here](https://github.com/p1k0chu/bac-tracker)

# Installation Instructions
~~Download bac-tracker.zip from [latest release](https://github.com/TheTalkingMime/bac-tracker/releases).~~
Download source code.
1. Unzip `bac-tracker.zip`. You should have a `data` folder, `settings` folder, and an `src` folder.
2. Get a credentials json by following the instructions [here](https://www.youtube.com/watch?v=KIAo3Lgsk_Q), you only need to watch until 1:40 in the video. The rest of the video is specific to reset-tracker.
3. Put that json into the settings folder
4. Rename that json to `credentials.json`
5. Make a copy of the [1.21 Template](https://docs.google.com/spreadsheets/d/1Gyp1atdQ7QLEWRHBQ2AQFaTcg38jzZFPvaCOE4OeJhI/edit?gid=37686975#gid=37686975)
6. Open `credentials.json`
7. Inside you will find a field called `"client_email"` copy the associated value, and share it with your spreadsheet.
8. Rename `sample_settings.json` to `settings.json`. Open `settings.json`. 
9. Copy the spreadsheet link and paste it in between the quotation marks for the `"spreadsheet-link"` field.
10. Navigate to your server file panel. Copy the full world file path. (Ex: `/default/world/`)
11. Paste the file path into the `settings.json` value for `"remote_world_path"`.
12. Your server should provide you with a host URL, username, and password for FTP access.
Paste those fields into `host`, `username`, and `password` in `settings.json`. Modify the value for `port` if necessary (most servers deafault to 21).
  - If for whatever reason you want to use this branch on a singleplayer world, set `["ftp"]["enabled"]` to `false` and it will run as normal.
13. ~~Run tracker.exe and hope it all works~~
  - You can also run the tracker via the source code. Useful for running on macOS or Linux.
    a. Download the source code, or clone the repository.
    b. Configure `settings.json` and `credentials.json` as normal.
    c. Using your terminal, navigate to `bac-tracker/tracker/`
    d. Run `python3 src/tracker.py`
    e. To close the tracker press control + c.
14. If you encounter any errors send the latest.log in the (MCSR BAC Discord)[https://discord.gg/yGPXGtgYqT] to assist.
  - This branch isn't fully polished and errors will still ocassionally occur when the tracker downloads a file as its being written to. Restarting the tracker usually fixes.

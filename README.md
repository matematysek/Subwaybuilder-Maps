# Subway Builder – Map Mods collection: Prague, Brno, Bratislava

**These mods are modified Versions of mhmoellers Copenhagen City Mod.**
**You can find the original Copenhagen City Mod (published under the MIT license as far as i know) here: https://github.com/mhmoeller/SubwayBuilder-CPH**

## Cities and Data Quality

This pack includes Prague, Brno (Czechia) and Bratislava (Slovakia) each with space around the cities for commuter trains.

The Data has been generated with early commute and resident data generation scripts from Kronifers subwaybuilder patcher. (https://github.com/Kronifer/subwaybuilder-patcher) so **the commute and residents data is not based on real census data and the resolution is quite inconsistent, but it is mostly reasonable and playable.**

There are some - lets call it - unconventional people counts in some places - i have tried fixing some of them, but right not there is not very much i can do.

## Features

 Automated Installer: Includes a custom Node.js script that automatically places large data files in the correct game directories (cities/data/CPH) while keeping the mod manageable. Portable Map Server: Generates a serve.bat file that makes hosting the local map tiles (PMTiles) easy.

 **All of these scripts used in the mods and for data generation are from https://github.com/mhmoeller/SubwayBuilder-CPH and https://github.com/Kronifer/subwaybuilder-patcher, and i am very glad they can be adapted to other cities without many modifications.Thanks to mhmoeller, Kronifer and the Subwaybuilder modding community for making this possible!**


Subway Builder (the game)
Node.js (Required to run the installer script)
The files from this repository.

## Installation
The installation process is automated to ensure all data files end up in the correct folders.

1. Make sure all requirements are met

2. **Download the Code, and unzip it.**

3. **Move all the city mods you want to play to the games mods folder**(not alltiles, as this folder is just required to host the tiles of the maps and is not a mod)

4. Run the Installer (install.sh /install.bat) in every city folder.

#### Windows:
Double-click install.bat inside the CPH folder.
#### macOS:

Method 1 (Recommended): Open Terminal, navigate to the CPH folder and run:
```
./install.sh
```
Method 2: Right-click install.sh, select "Open With" → "Terminal"

Method 3: In Finder, open the CPH folder, then open Terminal and drag install.sh into the Terminal window, press Enter

If you get a "permission denied" error, try the linux solution, it worked for me. The command for linux (chmod +x) gives the program permission to run.

#### Linux:

Open a terminal in the CPH folder and run:
```
chmod +x install.sh
./install.sh
```
Wait for the script to finish. It will:
Move the heavy data files (.gz) to the cities/data/(Whatever city you are adding) folder.
Generate a serve.bat or serve.sh file for you.

## How to Play
Start the Map Server:
Locate the serve.bat or serve.sh file (in the alltiles folder)
Double-click it to start the local server.
This will host all tiles of all cities in the pack, even if not downloaded.
If this does not work, start it the same way install.bat or install.sh was.
Keep this window open while playing.
Start the Game:
Open Subway Builder.
Go to Mods and enable the city (if listed).
Close the game entirely.
Restart the game.
Start a New Game and select CPH as your city.

5. **Start the server** by executing pmtiles in your alltiles folder, either by executing serve.sh / serve.bat in the alltiles folder or using this command in the alltiles folder **./pmtiles serve . --port 8081 --cors="*" on mac or pmtiles.exe serve . --port 8081 --cors="*" on windows** or at least i think thats what the command for windows would look like...

### Notes
Data Files: The installer moves ocean_depth_index.json.gz, roads.geojson.gz, buildings_index.json.gz, etc., to the game's internal data structure.

Map Server: The pmtiles.exe utility is included to serve the map tiles locally. The serve.bat script launches this on port 8081 with CORS enabled, which is required for the game to display the background map.

Uninstalling: To remove a map, delete the corresponding folder from your mods directory and delete the city folder from %APPDATA%\metro-maker4\cities\data\, or on Mac: Library/Application Support/metro-maker4/cities/data

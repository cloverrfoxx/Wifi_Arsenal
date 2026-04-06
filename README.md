WifiArsenal - Tactical Wi-Fi Manager for Grey Hack

Note: This is a script written in GreyScript for the video game Grey Hack. It is not a real-world tool.


---


The Problem

The way most players start out (including myself) is usually to set up a script that blindly rotates through cracked Wi-Fi networks on a timer. The problem with this is that if you're just looping through a list of networks, you're eventually going to land back on a router you've accessed before, which can complete passive traces against you, or expose you to other players hunting you.

WifiArsenal changes this workflow. It treats cracked networks sort of like consumable resources. As new ones occasionally pop up I think this is a valid solution.

Instead of an endless loop, you build up an arsenal of compromised networks. When you do something risky and suspect your IP might have leaked, you hit the panic button to "Burn & Hop". The script instantly kicks you to a clean network and flags your previous one as burned in your database, making sure this tool never connects to that compromised router again.
You can of course still manually connect to any wifi network, and you can revive burnt networks in the tool if you have reason to, but it's not recommended.

Features

    Background Scanner: Spawns a detached terminal that passively injects packets, cracks passwords, and adds clean networks to your database while you do other things.

    Burn & Hop: A panic button that flags your current network as compromised and jumps to a fresh connection.

    Failsafes: Prevents you from burning your last available network so you don't accidentally lock yourself out of the internet.

    Database Management: Menu to view your available and burned networks, with the option to revive burned access points. Probably shouldn't though, just saying.

    Compact UI: Built to fit cleanly inside the default Grey Hack terminal window without breaking formatting.

Main Menu

    [1] Start Background Scan: Spawns a background process that scans your area, testing networks from strongest signal to weakest. It auto-cracks them and updates your database. You can safely minimize this terminal while it runs.

    [2] Burn & Hop: If you think you've been spotted, hit 2 and press Enter. It will identify your current router, mark it as BURNED, and jump to the next clean network. You can also specify an ID to burn a different network.

    [3] List Arsenal: Check your available and burned networks. You can revive specific networks by ID or revive all of them, though you'll get an OPSEC warning first.

    [4] Auto-Rotate: Launches the legacy timed rotation loop. Warning: Using this without burning networks defeats the stealth purpose of the tool.

    [5] Exit: Closes the script.

Background Arguments

You probably won't need to run these manually since the menu handles it, but they're there if you want to write your own wrapper scripts:

    wifiarsenal -scan [min_power]: Runs the scanner (e.g., wifiarsenal -scan 50 only targets networks with 50%+ signal).

    wifiarsenal -rotate [minutes] [min_power]: Runs the legacy rotator.

Configuration

The script saves your database to your home directory by default (~/.wifinetworks.txt). If you want to change where the file lives, just open the source code and edit the STORAGE_PATH variable near the top.
Remove the '.' before the name (~/wifinetworks.txt) if you want to see it in FileExplorer.exe. I've hidden it by default to reduce visual clutter.

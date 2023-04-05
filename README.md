# InstallPepegaLinux

Tutorial for installing and configuring NFS Pro Street Pepega Mod on Linux.

If you don't know what the Pro Street Pepega mod is, it's basically a community-created modpack that puts a lot of memes into the game, as well as new cars, improved graphics, new kings, a completely custom campaign and a lot more. You can find more information and downloads at [pepegamod.com](https://pepegamod.com/).

The Pro Street Pepega Mod is the successor of the legendary Most Wanted Pepega Mod released in 2020.

This instruction has been tested on Steam Deck/SteamOS 3.4.6. May or may not require additional steps for different distros.

## Pre-requisites

- Lutris
- The Need for Speed Pro Street Pepega version 1.1 installer
- The folder "Linux-only" from the installer
- Recommended external kb + mouse on Steam Deck for comfort

## Installing Pro Street Pepega

For the installer part you have 2 options, you either prepare a Pro Street Pepega install on Windows and copy it to the Steam Deck or you do the complete installation on the Steam Deck. I would recommend preparing everything on Windows if you don't know much about Lutris.

**Install method A: Windows + copy**

1. Run the installer and install Pro Street Pepega to an EMPTY folder. ALL the necessary game files are included with the installer.

  Make sure you select the input option "XBOX Controller" and "Fullscreen" during the installation! These settings matter to make sure the buttons of the Steam Deck are     properly mapped without any tweaking.

2. Copy the contents of the "Linux-only" folder to the root of the Pro Street Pepega mod.
  The "Linux-only" folder contains a slightly modified nfs.exe and a d3dx9_34.dll file that we need later. This copy will overwrite nfs.exe which is what we want.
  
3. Copy your prepared Pro Street Pepega folder to the Steam Deck.

**Install method B: Steam Deck**

1. In lutris, add a new game -> Add locally installed game with settings as below:

  *Game info*:
  
  Name: whatever you want
  
  Runner: Wine

  *Game options*:

  Executable:
  Select the installer.exe from the Pro Street Pepega installer.
  
  In my case I extracted the setup in my Downloads folder so the Executable selected was the following:
  If your install folder is in a different location, make sure you point Lutris to the right Executables and folders.
```
/home/deck/Downloads/NFS_PSPE_V1.1_Release/installer.exe
```

  **Runner options**:
  Wine version - lutris.fshack-7.2-x86_64

  **System options**: nothing to change here

2. Save config, select the game from your library and press Play. The Pro Street Pepega installer will now launch.

3. Select an EMPTY folder when deciding where to install Pro Street Pepega. I highly recommend installing it on a location that's outside the Wine environment by using the Z: drive

4. Make sure you select "XBOX Controller" and "Fullscreen" during the setup.

5. Copy the files "nfs.exe" and "d3dx9_34.dll" from the install folder to the root of your new install of Pro Street Pepega.

## Getting Pro Street Pepega running with Lutris

1. In lutris, add a new game -> Add locally installed game with settings as below:

  **Game info**:
  
  Name: whatever you want
  
  Runner: Wine

  **Game options**:

  Executable:
  - if you have a working installer, copy the path to Setup.exe here;
  - if you copied the files already, select the path to speed.exe:
```
/home/deck/Games/nfsps_pepega/speed.exe
```

  Working directory:
```
/home/deck/Games/nfsps_pepega
```

  Wine prefix:
```
/home/deck/Games/nfsps_pepega
```

  Prefix architecture: Auto (default)


  **Runner options**:
  Wine version - lutris.fshack-7.2-x86_64

  **System options**: nothing to change here

4. Save config, select the game from your library and press Play. If you copied a prepared installation, skip to step 9.

5. If Wine wants to install any additional packages (i.e. Mono), let it do so.

6. If you're running an installer, as install location choose your wine prefix:
```
Z:\home\deck\Games\nfsmw_pepega
```
  In my case the directory was not visible, just input it manually.

7. Don't install any additional packages like DirectX if prompted.

8. After installation is complete, change the Executable path to speed.exe like in step 3.

9. Try playing the game. At this point Wine should configure the prefix and Most Wanted should start in it's whole 640x480 glory.
  If you copied a vanilla installation, it *should* also run. If you copied Pepega-patched installation, it will probably run, but you will definitely experience glitches like out-of-scale intro movies and missing car models. This is fine!

10. If you ran the game and created a profile, delete it and quit.

11. Back in Lutris, right-click the game and select Configure.

12. In Game options, set the Executable to Pepega Mod Version 2 Installer.exe, save and run the game.
  Note: Text in installer may not render correctly, in my case it was all black-on-black text, but all necesarry options are visible.

  Navigate like so:
```
1. Next
2. scroll readme -> Next
3. in path manually input your folder: Z:\home\deck\Games\nfsmw_pepega
4. uncheck the tickbox to backup files
5. on next screen, leave checkboxes as they are -> Next
6. same on next screen unless you want to change some options -> Install
```

13. If it looks like the installer is hung at 0%, just give it some time and it will start eventually.

14. When progress reaches 100%, check the installation log and if you notice a lot of errors like: `Copy failed:java.io.IOException: No more files`,
just finish the installer, and then copy+overwrite all files from `PepegaModFiles` folder to your game folder.

15. Now, copy+overwrite the files from patch 2.0.1 directory - choose if you want light cones or not (I recommend using them).

16. Back in game configuration, switch the executable back to speed.exe.

17. In Lutris menu, press the up arrow next to Wine logo, and select 'Wine configuration'.

18. Go to 'Libraries' tab, and in 'New override for library' find and Add overrides for following libs:

```
D3DX9_43
dinput8
winhttp
```
  Apply and close the config.

21. Save the changes and try running the game. If you followed the instruction correctly, you should be greeted by Team Pepega splash screen.

22. If you're on Steam Deck, in Lutris menu right-click the game and select "Create Steam shortcut". Now you can exit to Game Mode and you'll see a new non-steam game in your library, with full gamepad support on default settings.

23. Congratulations, and have fun beating the new kings!

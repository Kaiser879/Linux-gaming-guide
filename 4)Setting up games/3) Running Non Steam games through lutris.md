- Lutris is an open-source game launcher and management platform for Linux that helps install, organize, and run games from multiple sources, including Steam, GOG, Epic Games, emulators, and Windows games through Wine.
- We can use Lutris to run Games that were sourced outside of steam
- Open Lutris(It is a good practice to run lutris by running it from terminal so we can see the logs and errors upfront )
- Ge-proton should be the default runner for Lutris
- You can connect your GOG account here to directly source games from there

## Running a Pre installed/Portable installs of games
### Game info
- Click on the plus icon at the top left corner of the window
- click on add locally installed games
- Input the Correct name of the game(important for lutris to fetch metadata)
- in runner select Wine(runs windows games)

### Game options
- Executable: Navigate to exe file of the game and select it
- Arguments : Leave blank for now
- Working Directory:Navigate to the working directory and select it (working directory is the directory where the exe file is located )
- Wine prefix: Leave this empty so lutris will create a fresh wine prefix for the game(You can learn what a wine prefix is and how to create it manually in the tweaks sections, but for now lutris manages it automatically for you )

### Runner options
- Wine version: select proton ge latest as the runner
- click save.(all of the other settings will be explained in the tweaks section of the guide)

### Running the game 
- Your game should show up in your lutris library now 
- Click play for the game to run
- It might take some time to run a game for first time since lutris will be downloading some dependencies
- You can observe what exactly lutris is going by right clicking at the game and opening logs 
- It is necessary to past  the logs when asking for help online
- Refer to the tweaks and troubleshooting section if the game dosent work

## Installing games through a installer and running the game
- If you don't have a portable copy of the game but a installer like a GOG game installer or a repack
- Click on the plus icon on the top left corner of the windows 
- Click on Install a windows games from an exe 
- Input games name hit install
- select a installation directory preferably create a game folder in the home directory 
- Navigate and select The setup.exe file 
- after completing installation click close
- Game should show up in lutris library but there are still things yet to be done 
- right click on the game and open configuration

### Game info 
- Select wine as runner 

### Game Options
- Executable: select the exe file of the game that you just installed
- Working directory : select working directory of the game you just installed ( working directory is the directory that contains the exe file )
- Leave the wine prefix to default ( You can learn what a wine prefix is and how to create it manually in the tweaks sections, but for now lutris manages it automatically for you )

### Runner Options 
- Wine version : Select it to be GE-PROTON 
- leave everyting to default all of the settings will be covered  in tweaks section in detail 
- click save 

## Running the game 
- Click on the game and hit launch 
- Game should run
- Refer to tweaks and troubleshooting section of you face any problem

# Note:
- It is recommended to use portable games files or reputed Installers like GOG insted of repacks since repacks are more prone to failure and errors while installation. 
- Since you installed all essential gaming  packages steam should be installed
- Open steam
- login and open steam settings/compatibility and select the latest proton version as compatibility layer
- Install the game that you wanna play
- Hit play and your game should run
- Not all games might run and some games need specific tweaks for them to run 

## Usage of proton db
- it is recommended to visit https://www.protondb.com/ to check for what tweaks users have used to run specific games
- Proton db has classified games into 4 categories such as
- 1)platinum:which means that the games run out of box without any tweaks
- 2)gold: games that run after doing some tweaks
- 3)broked : games that are broken on linux 
- 4)Native : games that have native linux suport
- On proton db users often mention the tweaks they have used to make the game run with there system info 

#### How to install proton-ge for steam
- Proton-GE is a an unofficial fork of proton created and maintained by a solo dev named Glorious Eggroll
- Proton GE also comes with extra components built in. Stuff such as media playback fixes, AMD FSR patches, and a “proton-fixes” system that applies fixes on a per-game basis, allowing certain games to work with Proton GE even though they don’t work with Valve’s Proton.
- In general, Proton GE can allow you to enjoy a game that doesn’t work with Valve’s Proton or offer better performance compared to Valve’s Proton.
- To install Proton-GE we will need a package named ProtonUp-QT
- ```bash
  sudo pacman -S protonup-qt //run this to install protonup-qt 
  ```
-  open protonup-qt and it will automatically detect your steam folder
- Click on add version 
- select ge proton as compatibility tool and select the latest ge proton version
- click install , downloading and installation will start 
- After installation go into steam settings/compatibility to select proton-ge as the compatibility tool for your steam games.
- In This way you can install multiple proton-ge version as per your need



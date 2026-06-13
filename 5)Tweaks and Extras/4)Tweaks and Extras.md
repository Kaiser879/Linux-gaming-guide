## Understanding Wine/Proton and Manually Creating a wine prefix
- As covered in section 9.2 Proton/wine is a compatblity layer for windows games on linux. 
- A WINE prefix is a folder that contains all of the WINE configurations as well as all of the Windows pieces that WINE uses for compatibility, including libraries and a registry.
- Think of it as a directory we create to simulate windows environment for windows apps to function though Wine.

#### how to create a wine prefix
- for example Lets say i have a app called "Winapp" and i want to create a wine prefix for it and run it without using any external launcher .
- ```bash
WINEPREFIX=$HOME/prefixes/Winapp wineboot //We use this command to create a wineprefix and initialize it 
```
- This command tells wine to use $HOME/prefixes/Winapp as the windows installation directory while "wineboot" wineboot initialises wine inside that directory 


#### how to configure the wine prefix 
- To configure the wine prefix and change some settings we use command 
- ```bash
  
  ```


## Difference between Multiple proton versions 

## General tweaks 

## Prime-render-offload

## Game-scope

## Mango-HUD

## Environment Variables

## Win 32


## Better Power profile management with TLP

## How to Disable Cpu boost

##


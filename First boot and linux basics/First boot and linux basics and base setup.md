## first boot
- now that you have restarted your device 
- you will find user on the limine screen 
- navigate  over Cachy os with arrow keys and hit enter

## Login screen/Display manager
- now you will be greeted with a login screen 
- this is as a display manager
- Display manager:- it is a program that provides a graphical login screen on linux  , it starts the graphical environment , lets you choose a user , handles authentication, then launches a desktop environment or window manager of choice.
- type your password that we entered while the installation process and hit enter

## Welcome to linux / Walkthrough
- hey now you are part of the linux community 
- Cachy os will greet you with a cachy os hello screen
  ![[Screenshot_20260525_110245.png]]
- Cachy OS Hello is a gui tool that helps you do all sorts of stuff on linux 
- Though we wont be using it often , it makes some things less tedious to do on our  system 
- keeping it aside first thing i want you to do is to make yourself home in this new system 

### Changing wallpaper and the bottom panel 
- As a first step lets try Changing the wallpaper and cutomising the bottom panel on our screen 
- to do that just 1) just right click on the home screen
- ![[Screenshot_20260525_110938.png]]
- 2) select desktop and wallpaper (you can also open it with shortcut Ctrl+Shift+D)
- 3)![[Pasted image 20260525111208.png]]
-  Select one of the pre loaded wallpapers or Download one from the internet and use the add button to set  the wallpaper
- Now lets customise the bottom panel for a bit 
- right click on bottom panel , then click on show panel configuration 
- ![[Pasted image 20260525111441.png]]
- mess with some of the settings and customise it to your liking 
- Just like this Explore the Ui of your system and become comfortable with it 


### Things to try now 
- check if all of your shortcuts and keyboard keys are working as you want , you can customize then how you want through shortcuts menu in system setting
- try taking a screenshot with PRTSC key
- explore display configuration setting to manage refresh rate and scaling
- explore appearance and style settings to customise look and feel of your desktop, there are thousands of community made themes ,icon packs , window decoration etc to choose from ,
- ![[Pasted image 20260525192629.png]]
- 

### The terminal/shell 
- on linux there is no running away from the terminal , a terminal is a essential tool that provides you a text based interface for interacting with your computer with help of commands
- with terminal you can perform all sorts of tasks like installing software, configuring  system, and perform system tasks 
- Every terminal runs a Shell , A shell is a command interpreter that reads user command and tells the OS what actions to perform, for eg bash,fish,Zsh . Cachy OS uses Fish by Default.
- To open your terminal Search Allacritty in Application menu and open it
- ![[Screenshot_20260525_112751.png]]
- you can also pin it to task bar as we will using it often 
- Allacritty is a fast terminal emulator that comes pre configured with Cachy OS
- When you open the terminal you will see as your system information displayed there .
- Allacritty is using a preconfigured command line tool called "fast fetch" that Displays system information in a formatted layout 
- you can type "fast fetch" again in your terminal to get this output 
- When ever asking for help on any linux forum use a screenshot of this fast fetch output so that other people can understand your system and help you accordingly


### First command/ Updating system 
 our first command that we are going to type in this terminal is 
 "sudo pacman -Syu"
 here sudo:- is a command use to run something with admin privileges
 pacman :- is our package manager used by Arch linux and arch based distros like Cachy os
 -S :- is a command to instruct pacman to synchronise packages from repositories
 -y:- is a command to instruct  pacman to refresh package database
-u:- instructs pacman to upgrade all installed packages that have updates available 
So combined "sudo pacman -Syu " updates all package database and upgrades all installed packages on system (it is Linux equivalent of updating you system on windows)

type this in your terminal and hit enter for the update to start
![[Pasted image 20260525114848.png]]
since on my system was already up to date it did nothing 

### why you should update frequently and do a full system upgrade 
- Cachy os is a rolling release distro and receives update frequently 
- Every native arch package is shipped through pacman is everything is upgraded all at once  
- you should never do a partial upgrade with sudo pacman -Sy as it can create break dependency and at extreme times seriously break the system 

### How to install packages/Software:
 before understanding how to install package, it is important to understand where it comes from. on arch based distro from offical arch repos or AUR or building from source code 
 - Offical Arch repo: collection of packages maintained and tested by the arch linux team and trusted maintainers.
 - Building from source:- insted of downloading a prebuilt package , we can compile the source code directly on our machine and build that package.
 - AUR(Arch User Repository): a community mainted collection of build scripts that help users install packages not officially supported by arch repos

### how to install packages from Arch repos 
- to install we will be using  command "pacman -S _package_name1_ _package_name2_ ..."
- We can install multiple packages with this command
- lets try installing a media player like VLC for example 
- type "sudo pacman -S vlc" and hit enter in your terminal 
- hit enter to procced with installation 
- now you can look in application menu and you vlc will showup there 
- question: how do i know if the package i want is available in arch repos 
- answer:- "pacman -Ss package-name" it will search if there is a package matching the one you have entered in the database and will display its full name and info
- ![[Pasted image 20260525125853.png]]
- you also search about it on arch package website
- learning syntax is of pacman is essential to using this system , but you dont learn everything at once , everytime you need to do something with pacman just search it up and you will learn the syntax in no time 
- here are some commonly used commands:
- ##### pacman Cheat Sheet
###### Update System
```bash
pacman -Syu
```

###### List Installed Packages
```bash
pacman -Q
```

##### Search Installed Packages
```bash
pacman -Qs <name>
```

##### Search All Packages
```bash
pacman -Ss <name>
```

##### Install a Package
```bash
pacman -S <name>
```

###### Remove Package + Dependencies + Config Backups
```bash
pacman -Rns <name>
```

##### Clean Old Packages from Cache
```bash
pacman -Sc
```

---

##### Extras

| Command                         | Description                           |
| ------------------------------- | ------------------------------------- |
| `pacman -Qi <name>`             | Detailed info on an installed package |
| `pacman -Si <name>`             | Detailed info from the remote repo    |
| `pacman -Qdtq \| pacman -Rns -` | Pipe orphans directly into removal    |
| `pacman -Scc`                   | Clear the entire cache (aggressive)   |

### How to build package from source (optional , needs familiarity with git and github)
- We will use a Tool makepkg it is a built in tool for building packages.
- this tool reads a PKGBUILD file and produces a package
- make sure that base-devel is installed 
- ```bash
pacman -S base-devel
```
- get the source 
- ```bash
  git clone https://github.com/somedev/someproject
cd someproject 
  ```
  
- ```bash
  makepkg -si
  ```
build and install package
### how to install packages From Aur
- Unlike Pacman where compiled binaries are stored on Arch servers , AUR stores Pkg-builds(shell scripts) that describes how to build a package. Then actual source code is fetched from original developers git repo during build.
- To automate this process insted of building the package manually like we did above we will use a AUR helper like Paru or yay.
- A AUR helper is a tool that automates the process of fetching both the PKGBUILD from AUR and source from git repo and makes it easy for use to install
- Paru is the aur helper that comes pre installed on Cachy os 
- Paru has same syntax and flags as pacman and can be used similarly 
- ```bash
   paru -S spotify
  ```
  To install spotify from AUR
- AUR is a user User maintained repository and anybody can submit packages to it 
- it is a good practice to read the PKGBUILD before installing anything , also be sure to check comment section of the package for issues 
- some packages are directly maintained by corporation themselves on AUR eg google maintains chrome , Microsoft maintains VS code ,
- https://aur.archlinux.org/ you can search about every AUR package and read about it here


### Priority order to get packages 
1) you should always prefer to get packages from official arch repo through pacman over anything else 
2) you should get the package from AUR through paru if the package is not available in official repo but is actively maintained in AUR
3) You might find multiple build of same software on arch , prefer the one that is more popular and is maintained frequently 
4) When AUR dosent help resort to building from package from source 

### Exploring file system 
- ```bash
  /
├── bin/        # essential binaries (ls, cat, cp...)
├── boot/       # kernel, initramfs, bootloader (GRUB)
├── dev/        # device files (disks, USB, TTY...)
├── etc/        # system-wide config files
├── home/       # user home directories
│   └── user/
│       ├── Documents/
│       ├── Downloads/
│       └── ...
├── lib/        # essential libraries for /bin and /sbin
├── media/      # auto-mounted removable drives (USB, CD)
├── mnt/        # manual mount points
├── opt/        # optional/third party software
├── proc/       # virtual fs — live kernel & process info
├── root/       # home directory of the root user
├── run/        # runtime data (PIDs, sockets)
├── srv/        # data for services (web, ftp servers)
├── sys/        # virtual fs — hardware & kernel info
├── tmp/        # temporary files (cleared on reboot)
├── usr/        # user utilities and applications
│   ├── bin/    # most user commands live here
│   ├── lib/    # libraries for /usr/bin
│   ├── local/  # locally compiled software
│   └── share/  # shared data (icons, docs, themes)
└── var/        # variable data — changes constantly
    ├── log/    # system logs
    ├── cache/  # application cache
    └── spool/  # print/mail queues 
    ```
This is the file system hierarchy standard which is same across all distros (except nixos)

# Exploring the File System through terminal basics

- You can explore your file system through your terminal 
- ```bash
  ls  // is used to list directory content
  cd // is used to change directory 
  cd ~ // to go to home directory
  pwd // used to print working directory 
  ```
- here is a example open your terminal and type "pwd" it should print home/username as it is the default working directory
- then type "ls" to list all directory content 
- ```bash
 .cache
 .config
 .local
 .pki
 .var
 Desktop
󰲂 Documents
󰉍 Downloads
󱍙 Music
󰉏 Pictures
 Projects
 Public
 Templates
 Videos
󱆃 .bash_logout
󱆃 .bash_profile
󱆃 .bashrc
 .gtkrc-2.0
󱆃 .zshrc
  ```
  - it should print content like this 
  - now try getting into your Pictures directory by doing 
  - ```bash
    cd Pictures/Screenshots 
    ```
    - you can also use the Tab key to explore the directories while you type 
    - ```bash
      ls 
      ```
      to list all screenshots 
    - type screenshot file name to open it from terminal


### Exploring file system through Dolphin(kde file manager)
- explore file manager 
- try copy pasting stuff 
- alt+shift+f4 to open terminal with chosen directory as a working directory 

### Executing apps through terminal 
- you can execute every app from terminal by just typing the name of app of app inn terminal 
- like ```firefox
- to open Firefox through terminal 
- Use this when you need to trouble shoot stuff as it will print out logs of the app in terminal for you to understand what is wrong
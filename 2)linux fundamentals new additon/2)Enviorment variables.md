## What is a environment variable

- Environment variable is a named value that a program reads when it starts . in simpler terms it is a variable with a name and a value
- Examples
- ```bash
  echo $HOME
  echo $USER
  echo $SHELL
  echo $PATH
  ```

## how to check environment variables

- ```bash
  printenv 
  ```
- Use this command in your terminal to print all environment variable with value 
- ```bash
  echo $VAR #used to check a single variable 
  ```
## Why do we use environment variables and what are the use cases
- Environment variables are used to pass data between system process and set global defaults for applications to use 
- there are multiple use cases for environment variables some of them are as follows 
- ```bash
  USER=kunal #Specfies current user which programs can read 
  ```
- ```bash
  SHELL=/bin/fish #specfies path to Users default login shell which programs can    read
  ``` 
- ```bash
  GTK_THEME=Breeze-Dark firefox // Used to specify the theme firefox should use    for this sessions
    ```
- ```bash
  MANGOHUD=1 %command% #used to enable a optional feature for steam 
  ```

## How to set environment variables 

#### For  a single command
- ```bash
  EDITOR=nano git commit #sets the enviorment variable for the single command 
  ```

#### For the current shell
- ```bash
  export EDITOR=nano #sets the command for current shell 
  ```
note : export is a shell built-in command that marks a variable as an environment variable, making it available to programs launched from the current shell. 
#### To set permanently in shell config 
- User can edit  the shell config placed in ~/.config/fish/config.fish or ~/.bashrc and add the line "export EDITOR=nano" to set the Environment variable
- The environment variable is set every time you start a new shell

#### To set system wide
- can be defined in files such as 
- ```bash
  /etc/environment
  /etc/profile
  ```
- These are permanent and system wide

#### In applications
- Application can set environment variables that child process can inherit 
- for eg launch options in steam 
- ```bash
  MANGOHUD=1 %command%
  ```



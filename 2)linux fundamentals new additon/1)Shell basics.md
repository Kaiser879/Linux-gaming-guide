The terminal chapters so far have covered all terminal basics but now lets delve deeper, On what works under the hood called terminal.
Your terminal is the window through which you interact with the shell. The shell is what actually interprets and executes your commands.

## How does shell works
Terminal acts as a Input/Output medium , When you run a command for eg 
```bash
>  sudo pacman -Syu  //which you often run
```
Shell parses the text that you have entered in the Terminal and Then asks the kernel to execute the right programs.
This is a abstract way of saying what the actual shell does , It does way more than this but For this guide Undertstanding this enough.

## Different shells and there function(which one should you use)
Bash,Zsh, and Fish are the most popular choice when it comes to shell options.

We will cover them one by one 


### Bash
Bash is the most widely used command line shell, It is the default shell used my most Linux distributions.

Bash is highly compatible with Unix-like systems and is POSIX-compliant, which ensures that scripts written in Bash are portable and can run across different systems without issues.

bash lacks some modern features that are present in shells like fish or zsh but It is the most stable and widely documented command line shell.

Here is the link of official bash documentation if you want to learn more
https://www.gnu.org/software/bash/manual/html_node/index.html
### Zsh
Zsh offers many modern feature over bash such as Advance Auto-complete,Extensive Customisation ,a plugin system and many more.

Zsh is also compatible with bash scripts hence user can run most bash scripts with no problem 

More features introduce more complexity and hence a steeper learning curve 

### Fish
Fish focuses more on modern features with user friendly interface and out of box support of many features that you would have to configure manually in zsh or bash.

Fish is not POSIX-compliant, whereas Bash is, and Zsh is mostly compatible with Bash but does not fully adhere to POSIX standards.

fish comes with built in web-based configuration system where configuring it is as simple as ticking some boxes.

```bash
fish_config //use it to open web interface 
```
### Default shell of Cachy OS and shell choice 
Shell choice is subjective. Some users prefer Bash for its near-universal support, some prefer Zsh for its deep customisation, and some prefer Fish for its user friendliness out of the box.

Fish is the default shell on CachyOS, and most users are happy to keep it. However, the majority of shell documentation, forum answers, wiki pages, and scripts you will encounter online are written in Bash. When you search for a fix, a configuration tweak, or a setup guide, the answer will almost always be in Bash syntax. Understanding it is not optional it is the common language of the Linux ecosystem regardless of which shell you actually use day to day.

For that reason, whenever shell-specific syntax comes up in this guide, Bash will be covered first in full — Fish equivalent syntax will follow as a short note. Zsh is largely Bash-compatible and will not be covered separately; if you use Zsh, the Bash examples apply directly.

Note:Shell syntax => depends on shell
    Programs/Commands => Usually shell independent for end users.
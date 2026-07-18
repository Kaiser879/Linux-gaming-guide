Most of what runs on your distro doesn't run itself. It needs a service to start it . In this section we will see what are services/daemon. Remember seeing a screen full of rapidly scrolling white text on a black background , That was systemd at working initialising all services or daemons as we call them. (refer to 2.4.1)

## What are services / daemons
what systemd calls "service" was named daemon: any program that runs as a "background" process (without a terminal or user interface), commonly waiting for events to occur and offering services. 
## What is systemd
systemd is a software suite for system and service management on Linux built to unify service configuration and behavior across Linux distributions. 
As the first userspace process started by the Linux kernel (PID 1), systemd is responsible for initializing the system and starting the services required for a functioning operating system.
Controversial to the traditional UNIX philosophy of "do one thing well" systemd is not just limited to initialization but It also provides various daemons and utilities, including device management, login management, network connection management, and event logging.

### What is a service unit 
systemd works on units , units are objects that systemd manages. A unit is a configuration file that tells systemd how to manage a object.

```bash
sudo systemctl -t help 
```

the command above prints all the unit types as follows:
```bash
Available unit types:
service
mount
swap
socket
target
device
automount
timer
path
slice
scope
```
these are all the units types systemd manages but for the scope of this guide we will only be covering services 

service units have a .service extension , every unit has a name like NetworkManager.service or sshd.service .

#### Systemctl
Service units can be managed using the systemctl command.

Core Commands are:
```
systemctl status <service>     # shows if a service is runnning
systemctl start <service>      # start service (for this boot only)
systemctl stop <service>       # stop service
systemctl restart <service>    # stop the service then start
systemctl enable <service>     # start automatically on every boot
systemctl disable <service>    # stop starting automatically
systemctl enable --now <service> # enable + start in one shot
```

remember just starting a service wont persist across boot and just enabling a service wont start the service for this session

#### Journalctl
journal is a unifnied log of all services managed by systemd
journalctl can be used to inspect these logs 

core commands are 
```bash
journalctl -u <service>          # full log for one service
journalctl -u <service> -f       # follow live, like tail -f
journalctl -u <service> -b       # only since this boot
journalctl -xe                   # recent errors, system-wide
```


#### if Something is not working
general flow for troubleshooting is
- ```bash
  1) systemctl status <service>  #check if it is running
  2) systemctl start <service> #use this to start the service if its not running
  3) systemctl enable <service> #if check says the service is diabled to enable it 
  4) journalctl -u <service> -b # inspect the journal to see the problem 
  5) if you cant figure it out yourself then paste the journal output in a online forum while asking for help .
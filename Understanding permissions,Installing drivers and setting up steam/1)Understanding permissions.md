## Understanding permissions 
- Every file on Linux has 3 permission groups 
- 1) owner 2) group 3) other
- owner:user who created this file 
- group:every user on a system belongs to a group,when you create a user it makes a private group with the same name. file gets assigned to that group
- other: any other user that is neither a owner not belongs to the file group
- Each group can have 3 permissions:
  1)r(read) 2)w(write) 3)x(execute)
- Now open your terminal and run 
- ```bash
  ls -l   //this command is used to list permission with directory content
  ```
- You will see a output as ```drwxr-xr-x   - username 26 May 14:45 󰉍 Downloads``` for each piece of content  
- ```drwxr-xr-x``` is a permission string
- drwxr-xr-x
  ││  │  │ 
  ││  │  └── Other permissions (r-x)
  ││  └──── Group permissions (r-x)
  │└────── Owner permissions (rwx)
  │
  └───────── Directory (d)/file (-)
- here is how to read it 
- first char of this string indicates if it is a file or a directory 
- if its a directory it will be (d) and if it is a file it will be (-)
- then we will go in groups of 3
- first three char for owner(rwx), next three for group(r-x), next three for other(r-x)
- so here we have owner(rwx),group(r-x) and other(r-x)
- owner(rwx) means that owner has all permissions including read(r), write(w) and execute(x)(execute her for directory means the permission to access the file inside that directories)
- group(r-x) means that group has group only have read(r) and execute(x)  permission which means group users wont be able to write this directory
- other(r-x) means that other users only have read(r) and execute(x)  permission which means group users wont be able to write this directory
- together ```drwxr-xr-x``` means that this is a directory, (owner can read,write and execute), (group can read and execute), (other can read and execute)



## Using commands to modify permission of files and directory
- "chmod" is the command used to modify the permission //chmod(changemode)
- syntax: chmod {permission} {file}
- there are two ways to write permissions here : 1)symbolic 2)numeric
### symbolic command usage
- u = owner (user)
  g = group
  o = other
  a = all users
- + (add permission)
  = (remove permission)
  = (set exact permission)
- ```bash
  chmod u+x file.txt //(here we gave execute permission to the owner ) (u) to specify owner, (+) to specify that we want to add permission,(x) to specify that we will like to add execute permission 
  ```
- ```bash
  chmod o+r file.txt //here we gave read permission to others
  ```

### numeric command usage (optional)(useful if you want to read linux documentation)
- permissions can also be represented using numbers
- r = 4
  w = 2
  x = 1
- just add the values symbols up and we get value of the group
- 7 = rwx   r+w+x=4+2+1=7
  6 = rw-   r+w=4+2=6
  5 = r-x   r+x=4+1=5
  4 = r--   r=4
- rwxr-xr-x here is the permission string that we used earlier, to represent the string with a value , lump the values of addition of  symbols together 
- since rwx=7 and r-x=5 
- we can represent this string(rwxr-xr-x) as 755 where rwx is 7 and r-x is 5 hence the string becomes 755 
- usage: 
- ```bash
  chmod 755 file.txt \\ where 7=rwx 5=r-x  , 7 specifes to give (rwx) permission to owner , 5 specifes to give read and execute permission to group, next 5 specifies to give read and execute permission to  other
  ```
-  representation like 755/644 are commenly used in linux documentation and one should know how to use and read them 


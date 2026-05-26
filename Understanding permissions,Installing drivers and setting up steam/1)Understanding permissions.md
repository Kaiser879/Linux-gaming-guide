## Understanding permissions 
- Every file on Linux has 3 permission groups 
- 1) owner 2) group 3) other
- Each group can have 3 permissions:
  1)r(read) 2)w(write) 3)x(execute)
- Now open your terminal and run 
- ```bash
  ls -1    //this command is used to list permission with directory content
  ```
- You will see a output as ```drwxr-xr-x   - username 26 May 14:45 󰉍 Downloads``` for each piece content  
- ```drwxr-xr-x``` is a permission string
- here is how to read it 
- first char of this string indicates if it is a file or a directory 
- if its a directory it will be (d) and if it is a file it will be (-)
- then we will go in groups of 3
- first three char for owner(rwx), next three for group(r-x), next three for other(r-x)
- so here we have owner(rwx),group(r-x) and other(r-x)
- owner(rwx) means that owner has all permissions including read(r), write(w) and execute(x)
- group(r-x) means that group has group only have read(r) and execute(x)  permission which means group users wont be able to write this directory
- other(r-x) means that other users only have read(r) and execute(x)  permission which means group users wont be able to write this directory
- together ```drwxr-xr-x``` means that this is a directory, (owner can read,write and execute), (group can read and execute), (other can read and execute)
# Manage Authorization

## Project description
I work as a security professional at a large organization. I mainly work with the research team. Part of my job is to ensure users on this team are authorized with the appropriate permissions, to help keep the system secure. My task is to examine existing permissions on the file system. I’ll need to determine if the permissions match the authorization that should be given. If they do not match, I’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.

## Check file and directory details
The following screenshot shows how I navigated to, and showed the current permissions in the 'projects' folder.
<br>
![img_1](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/c0b1e6a7-0963-4e07-b9f7-e7b4a536c214)
The 'pwd' command shows me my current directory and the 'ls' command lists all files in the current directory.
<br>
I then use 'cd' to navigate into the 'projects' directory, and use the command 'ls -l' to list the contents of the directory, as well as the permissions for each file/directory.
<br><br>
I then use the command 'ls -la' to show the directory contents again, but this time hidden files/directories are also returned.
<br>
The results show that in the projects directory, there are one sub-directory 'drafts', four .txt files, and one hidden .txt file 'project_x.txt'.

## Describe the permissions string
The permission string is 10 characters long, and gives information about who is authorized to access a file, and their specific permissions.
<br>
**The first character** gives information about the file type. 
+ A 'd' means it is a directory
+ A '-' means it is a regular file
+ An 'l' means it is a symbolic link

**Characters 2 - 4** are the read(r), write(w) and execute(x) permissions for the user. If any of these characters are a hyphen (-), it means that specific permission has not been granted to the user.
<br><br>
**Characters 5 - 7** are the read(r), write(w) and execute(x) permissions for the group. If any of these characters are a hyphen (-), it means that specific permission has not been granted to the group.
<br><br>
**Characters 8 - 10** are the read(r), write(w) and execute(x) permissions for other. If any of these characters are a hyphen (-), it means that specific permission has not been granted for other.
<br><br>
For example, the permissions for "project_t.txt" are -rw-rw-r--.
<br>
The fist character in the string is a hyphen(-), meaning that project_t.txt is a file, rather than a directory.
<br><br>
Characters 2, 5 and 8 are 'r', meaning that user, group, and other all have read permission for this file.
<br><br>
Characters 3 and 6 are 'w', meaning that user and group have write permission for this file, while other does not.
<br><br>
No one has execute permission on this file.

## Change file permissions
The organisation has decided that other shouldn't have write permission on any of the files in this folder.
<br>
![img_2](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/1172c224-fb71-48e6-b3e9-3a9741d7dbad)
The screenshot above shows that other has write permission for the project_k.txt file.
<br><br>
The screenshot below shows how I modified the file permissions, and the results.
<br>
![img_3](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/e617183a-ae58-4313-bd38-2a4109bed1ff)
<br>
The "chmod o-w project_k.txt" command removes the write permission for 'other' from the file project_k.txt. 
+ chmod is a command use to alter permissions on a given file/directory.
+ The 'o' refers to 'other', whereas 'u' would refer to 'user' and 'g' would refer to 'group'.
+ '-w' means to take away the write permission. '+w' would add the write permission. '+-r/x' could also be used to add/remove the read/execute permissions for a file.
+ The file specified at the end of the command is the file that will have its permissions altered.
<br>
This could have also been achieved with the command "chmod 664 project_k.txt".

+ The 6s grants read (value 4) and write (value 2) permissions to the user and group
+ The 4 grants read permission to other
+ Execute permission has a value of 1, so granting all permissions for all users would require the command;
  + chmod 777 <file_name>


## Change file permissions on a hidden file
The hidden file .project_x.txt has been archived, and as such should not be written to by anyone. The organisation does however want user and group to have read permission.
![img_4](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/d0a51538-b13c-43a3-afe0-e956d2de8452)
The screenshot above shows that both the user and group have write permission, and only user has read permission. .poject_x.txt is identifiable as a hidden file as it begins with a period (.).
![img_5](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/800ef3fc-303a-4595-ba61-377cb7eeb417)
Here, I used the command "chmod ug-w .project_x.txt" to remove write permission for user and group.
I then used "chmod g+r .project_x.txt" to grant read permission to group.

## Change directory permissions
The organisation has decided that only the user should have execute permission for the 'drafts' directory.
![img_6](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/bff2389c-cb00-4b36-84bd-cbbf419f9e08)
We can identify 'drafts' as a directory, as its permission string begins with 'd'. The permission string also shows that the group currently has execute permission on the 'drafts' directory.
![img_7](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/6f9eb2a3-2a9f-4027-88b1-588eaf20f895)
The command "chmod g-x drafts" removes the execute permission from the group for the drafts directory.

## Summary
In this exercise I changed the permissions of files (some hidden), and directories, to match the authorization levels requested by my organisation. I started by listing the files in the 'projects' directory using the ls -l/ls -la command, and then used 'chmod' to change permissions for relevant files.

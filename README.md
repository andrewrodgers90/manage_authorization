# Manage Authorization

## Project description
I work as a security professional at a large organization. I mainly work with the research team. Part of my job is to ensure users on this team are authorized with the appropriate permissions, to help keep the system secure. My task is to examine existing permissions on the file system. I’ll need to determine if the permissions match the authorization that should be given. If they do not match, I’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.

## Check file and directory details
The following screenshot shows how I navigated to, and showed the current permissions in the 'projects' folder.
<br>
![img_1](https://github.com/andrewrodgers90/manage_authorization/assets/132149730/c0b1e6a7-0963-4e07-b9f7-e7b4a536c214)
The 'pwd' command shows me my current directory and the 'ls' command lists all sub-directories.
<br>
I then use 'cd' to navigate into the 'projects' directory, and use the command 'ls -l' to list the contents of the directory, as well as the permissions for each file/directory.
<br>
I then use the command 'ls -la' to show the contents again, but this time the result also returns any hidden files/directories.
<br>
The results show that in the projects directory, there are one sub-directory 'drafts', four .txt files, and one hidden .txt file 'project_x.txt'.

## Describe the permissions string
The permission string is 10 characters long, and gives information about who is authorized to access a file, and their specific permissions.
<br>
The first letter gives information about the file type. 
+ A 'd' means it is a directory
+ A '-' means it is a regular file
+ An 'l' means it is a symbolic link


## Change file permissions
[Add content here.]

## Change file permissions on a hidden file
[Add content here.]

## Change directory permissions
[Add content here.]

## Summary
[Add content here.]

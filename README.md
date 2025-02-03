# Managing Authorisation

## Objective  
In this project, I utilised Linux commands to manage authorisation.

Authorisation involves granting access to specific resources within a system, which is crucial for security. Without proper authorisation, any user could potentially access and modify files that belong to other users or the system itself, posing a significant security threat. Linux controls access to files and directories through permissions, which determine who can access and alter them. In this lab, I examined these permissions and adjusted the ownership of a file and a directory to restrict access appropriately.  
As a security analyst, it is vital to set the correct access permissions to safeguard sensitive data and ensure the system's overall security.  
This project was provisioned using Qwiklabs and hosted on Google Cloud.  

### Skills Learned

- Managing authorisation using Linux Bash shell commands  
- Adjusting directory permissions to control access for different user types, ensuring security and restricting unauthorised access  
- Understanding the importance of setting appropriate permissions to protect sensitive information and maintain system security  

### Tools and Environments Used

- Linux / Bash shell

## Scenario  
In this scenario, I needed to examine and manage the permissions for the files located in the `/home/researcher2/projects` directory, specifically for the `researcher2` user.  

The `researcher2` user is part of the `research_team` group.  

Firstly, I checked the permissions for all files in the directory, including hidden files, to ensure they matched the required authorisation levels. If any files had incorrect permissions, I adjusted them accordingly. Lastly, I reviewed the permissions of the `/home/researcher2/projects/drafts` directory and modified them to prevent any unauthorised access.  

**This hands-on project is broken down into four tasks in the following order:**

### Task 1: Check File and Directory Details  

In this task, I explored the permissions of the projects directory and its files starting from the current working directory at `/home/researcher2`.

I navigated to the projects directory and listed the contents, including their respective permissions.  
Here are the permissions for the files in the projects directory:  

![Z1](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/d0991645-5dd6-48c8-9cee-fb4a639b2807)

The listing of file permissions shows that the `research_team` owns the files in the projects directory.  

The shell command `ls -la` also revealed a hidden file `.project_x.txt`, as shown in the terminal output below:  

![Z2](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/c0df1d44-9ee3-4c20-b701-f1efbdfd0add)

### Task 2: Change File Permissions  
In this task, I identified files with incorrect permissions in the projects directory and adjusted them as necessary to eliminate unauthorised access and enhance system security.  

I checked whether any files in the projects directory granted write permissions to users other than the owner.  
From the previous terminal window, I noticed that the `project_k.txt` file had write permissions for other users. I modified the permissions of this file to ensure that users other than the owner did not have write permissions. To adjust the file permissions and remove write access for users classified as `other`, I used the command `chmod o-w project_k.txt`, as shown in the terminal below:  

![Z3](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/14ad6ccc-44c1-4e03-89f9-3c9cf0d374f8)

I also used the `chmod` command to adjust the permissions of the `project_m.txt` file. Originally, the group had read-only permissions on the file. However, since `project_m.txt` is a restricted file, it should not be readable or writable by the group or any other users, except the owner.

Thus, I modified the permissions of `project_m.txt` to remove both read and write permissions for the group.  

![Z4](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/50430ee2-bdd2-47ac-87ac-21f0547ef541)

### Task 3: Change File Permissions on a Hidden File  
In this task, I needed to verify if the hidden file `.project_x.txt` had incorrect permissions and then adjust them as necessary. It was important that this archived file did not allow any write operations by any user. However, both the user and the group should retain the ability to read the file.

I checked and modified the permissions of `.project_x.txt` to ensure that no users could write to it, while retaining read permissions for both the user and the group.  
The output of this operation is shown below:

![Z5](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/772c9bed-8136-42ad-8a45-48163332124d)

### Task 4: Change Directory Permissions  
In this task, I needed to adjust the permissions of a directory. Initially, I checked the group permissions of the `/home/researcher2/projects/drafts` directory and made modifications as necessary. I ensured that within the `projects` directory, specifically its subdirectory `drafts`, only the `researcher2` user retained access. This meant granting execute privileges solely to `researcher2` for the `drafts` directory and its contents.

I removed the execute permission for the group from the drafts directory, as the `projects` group had access to it. I used the shell command `chmod g-x drafts` to carry out this task.  

![Z6](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/265a3ec5-a31b-4e99-a4a1-b9eacd551d2b)

## Conclusion  

This project highlights my ability to effectively manage file and directory permissions in Linux using Bash shell commands. By controlling permissions, mitigating security risks, and safeguarding the integrity of organisational systems, I demonstrate comprehensive skills in ensuring system security and operational reliability.

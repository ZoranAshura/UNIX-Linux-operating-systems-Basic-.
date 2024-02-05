# Linux system installation and updates. Administration basics.

## Part 1. Installation of the OS

1. Install Ubuntu 20.04 Server LTS without GUI.
![Ubuntu_version](./images/1.1.png)

## Part 2. Creating a user

Create a user other than the one created during installation. 
The user must be added to **adm** group.

1. How many users exist before I add a new one.
![Number_of_users](./images/2.1.png)

2. A new user has been added.
![New_user_added](./images/2.2.png)

>  **adm**: Group adm is used for system monitoring tasks. Members of
> this group can read many log files in /var/log, and can use xconsole.
> Historically, /var/log was /usr/adm (and later /var/adm), thus the
> name of the group.
> 

3. Group names for the new user (before and after being added to the adm group)
![groups_before](./images/2.3.png)
![groups_after](./images/2.4.png)
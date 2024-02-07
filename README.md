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

## Part 3. Setting up the OS network

Set the machine name as user-1

1. Hostname before any changes
![kaleysha](./images/3.1.png)
2. After using the **set-hostname** command
![user-1](./images/3.2.png)

Set the time zone corresponding to your current location.
![current_time_zone](./images/3.3.png)

Output the names of the network interfaces using a console command.
![current_time_zone](./images/3.4.png)

> When a physical network interface is disconnected for any reason, like a hardware 
> failure or being physically detached from the network, the machine can’t use it for any 
> communication, even with itself.
> However, because the loopback interface is only an internal virtual 
> interface with no physical hardware, the machine can use it anytime to communicate with itself.
> This can help in troubleshooting scenarios where we want to isolate and identify if a network 
> issue is caused by an internal problem inside the machine network stack itself.

Use the console command to get the ip address of the device you are working on from the DHCP server.
![ip_address_from_DHCP_server](./images/3.5.png)

> A DHCP Server is **a network server that automatically provides and
> assigns IP addresses, default gateways and other network parameters to
> client devices**. It relies on the standard protocol known as Dynamic
> Host Configuration Protocol or DHCP to respond to broadcast queries by
> clients.

Define and display the external ip address of the gateway (ip) and 
the internal IP address of the gateway, aka default ip address (gw).
![public_ip](./images/3.6.png)
![private_ip](./images/3.7.png)

Set static (manually set, not received from DHCP server) ip, gw, dns settings 
(use public DNS servers, e.g. 1.1.1.1 or 8.8.8.8).
![Static_ip_gw_etc](./images/3.8.png)
![apply_changes](./images/3.9.png)

Reboot the virtual machine. Make sure that the static network settings (ip, gw, dns)
correspond to those set in the previous point.
![show_changes](./images/3.10.png)

Successfully ping 1.1.1.1 and ya.ru remote hosts and add a screenshot of 
the output command to the report. There should be "0% packet loss" phrase in command output.
![ping_ya.ru](./images/3.11.png)
![ping_1.1.1.1](./images/3.12.png)

## Part 4. OS Update

Update the system packages to the latest version
![update_command](./images/4.1.png)
![upgrade_command](./images/4.2.png)


## Part 5. Using the sudo command

Allow user created in Part 2 to execute sudo command.
![allow_newUser_using_sudo_command](./images/5.1.png)

In the report explain the true purpose of sudo command (don’t write about the fact that this word is "magic" one);
> The sudo command allows you to run programs with the security privileges of another user 
>(by default, as the superuser). It prompts you for your personal password and confirms your 
>request to execute a command by checking a file, called sudoers , which the system administrator configures

Change the OS hostname via the user created in Part 2 (using sudo):
1. First of all, I switched to superuser using **sudo su -** command
2. I set the password to **neUser**
![password_newUser](./images/5.2.png)
3. I switched to newUser and changed hostname
![hostname_newUser](./images/5.3.png)

## Part 6. Installing and configuring the time service

Set up the automatic time synchronisation service.
![check_status](./images/6.1.png)
![show_time](./images/6.2.png)

# Name : Chava Likhith
# Reg.no: 12209388
FTP Server 

An FTP server is a software application that runs on a physical or virtual machine, allowing users to transfer files between the server and client devices over a network (local area network or internet). It uses the FTP protocol, which follows a client-server architecture. Clients connect to the FTP server using FTP client software, enabling them to download or upload files, manage directories, or perform file operations.

Table of Contents

1. Step 1: Installing Operating System (Ubuntu 20.04).

2. Step 2: System Update.

3. Step 3: Installing Packages Like VSFTPD.

4. Step 4: Configure VSFTPD.
 
5. Step 5: Enable and disable Few options while Configure VSFTPD.

6. Step 6: Restart Service.

7. Step 7: Allow FTP Traffic Through the Firewall.
 
8. Step 8: Create the FTP user and Password.

9. Step 9: Make a directory.

10. Step 10: Test the FTP server.

11. Step 11: Install FileZilla.
 
12. Step 12: Add I.P address, Host and Password in filezilla.


Step 2: System Update:

Make sure your system is up to date before installing the VSFTPD. 

•	Sudo apt update.
•	Sudo apt upgrade.

![image](https://github.com/user-attachments/assets/913194af-fe85-45bc-b391-c3cd572f99d9)
![image](https://github.com/user-attachments/assets/e86d992e-bdd6-49f1-8c55-2953a2928256)
![image](https://github.com/user-attachments/assets/c8bc6f4e-fdc0-424e-aff1-a7545abb1d5f)

Step 3: Install Packages:

install VSFTPD (Very Secure FTP Daemon) to set up an FTP server on a Linux. VSFTPD enables the server to handle FTP connections, allowing users to upload, download, and manage files on the server over a network, whether it be locally or over the internet. With an FTP server, you can access files remotely from different devices, making it easier to share files between clients and the server. Users can connect via an FTP client (like FileZilla etc.) to upload or download files from anywhere.

•	Sudo apt install vsftpd.
•	Sudo systemctl status vsftpd.

![image](https://github.com/user-attachments/assets/31cd64eb-09ff-47f4-aea7-8bff8b56d363)

Step 4: Configure the Packages: 

•	Sudo nano /etc/vsftpd.conf. 

The command Sudo nano /etc/vsftpd.conf is used to open and edit the configuration file for the vsftpd FTP server using the nano text editor, with superuser privileges.

![image](https://github.com/user-attachments/assets/512e001e-412d-4068-b413-ad69df5c2cfe)

Step 5: Enable and disable Few options while Configure VSFTPD:

1.	anonymous_enable=NO: Disables anonymous FTP access to prevent unauthenticated users from logging in.

2.	local_enable=YES: Allows local users (with system accounts) to log in to the FTP server.

3.	write_enable=YES: Permits file uploads and modifications by users.

4.	chroot_local_user=YES: Restricts local users to their home directories, enhancing security by preventing access to other system files.

5.	pasv_enable=YES: Enables passive mode for FTP, which is useful for clients behind firewalls.

6.	pasv_min_port=10000: Sets the minimum port for passive FTP connections, used for data transfer.

7.	pasv_max_port=10100: Sets the maximum port for passive FTP connections, defining a controlled range for better firewall configuration.

![image](https://github.com/user-attachments/assets/6848240c-139c-45e3-bb04-2285a4fc521a)
![image](https://github.com/user-attachments/assets/cceb696a-7aa4-4871-a38e-f846a3c6f3ba)
![image](https://github.com/user-attachments/assets/d9f6738e-dc90-4f87-95c9-485f774d5266)
![image](https://github.com/user-attachments/assets/0073b3cb-defe-491d-879e-05839aac6ced)

Step 6: Restart Service:

After making modifications to the VSFTPD configuration file (e.g., /etc/vsftpd.conf), you need to restart the service for the changes to take effect.

make changes to service unit files or system configurations (like adding, modifying, or deleting service files), system needs to reload its configuration to apply those changes.

•	Sudo systemctl daemon-reload
•	Sudo systemctl restart vsftpd

![image](https://github.com/user-attachments/assets/80d73345-8c8a-4bdc-b65a-0f7338867f7c)

Step 7: Allow FTP Traffic Through the Firewall: 

•	sudo ufw allow 20/tcp: Allows incoming traffic on port 20 (FTP data transfer port) through the firewall.
•	sudo ufw allow 21/tcp: Allows incoming traffic on port 21 (FTP control port) through the firewall.
•	sudo ufw allow 10000:10100/tcp: Opens ports 10000 to 10100 for passive mode FTP data transfers.
•	sudo ufw enable: Enables the Uncomplicated Firewall (UFW), activating the firewall on your system.
•	sudo ufw reload: Reloads the UFW configuration to apply any changes made to firewall rules.
•	sudo ufw status: Displays the current status and active firewall rules on your system.

![image](https://github.com/user-attachments/assets/bfe850f1-9e2c-4d01-bb20-56f3a6c01f03)

Step 8: Create the FTP user and Password:

•	sudo adduser ftpuser

![image](https://github.com/user-attachments/assets/0955309d-b4ce-4ae1-bb9b-e187aa0c3034)

9. Step 9: Make a directory:

![image](https://github.com/user-attachments/assets/c8d99a3e-a8d3-47aa-99d3-1a9e08ac366f)

10. Step 10: Test the FTP server: 

•	ftp localhost
•	ifconfig

![image](https://github.com/user-attachments/assets/065ef971-3c74-4454-9233-45133d41206e)

Step 11: Install FileZilla: 

Install FileZilla using the Command “sudo apt install filezilla”

12. Step 12: Add I.P address, Host and Password in filezilla:

![image](https://github.com/user-attachments/assets/bf371d20-9069-4a43-a349-3830e19cb3cd)
![image](https://github.com/user-attachments/assets/268df47a-5860-42ef-8131-7818ec75363c)


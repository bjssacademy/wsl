# Windows Subsystem for Linux

## Installing WSL

1.	Open PowerShell as Administrator

> TIP: To find PowerShell, click on the magnifying glass icon in the bottom left of the screen and type in “powershell”

![alt text](image-1.png)
 
2.	In the PowerShell console, type ```wsl --install``` and press Enter:
 
 ![alt text](image-2.png)
 
3.	WSL will now start installing:


![alt text](image-3.png)
 
4.	Once complete, the system should ask you to reboot your computer. **Reboot your computer**.
5.	After restarting, Ubuntu should open and continue installing. It will ask you to create a username (all lower case) and a password.
    a.	If Ubuntu does *not* start, search for it in the menu and open it
        i.	No Ubuntu listed? Go to step 6
6.	After this is complete open PowerShell as Administrator
7.	Check your WSL version is version 2 by typing `wsl --list --verbose` and press Enter
    a.	If you get a message saying that WSL is installed but you have no distribution, type `wsl -–install -d ubuntu` and press Enter
    b.	If your version is showing as version 1, type `wsl --set-version Ubuntu 2` and press Enter
8.	Now open the Ubuntu app from the Start menu:
 
![alt text](image-4.png)

9.	In the Ubuntu console window that appears, run the following commands one by one:
 
 ```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get autoremove
 ```
 
## Accessing Files
Linux files can be accessed at the network path `\\wsl$\`. This can be entered into the File Explorer address bar:

![alt text](image-5.png)
 
Your installed Linux distros are listed, so you can access the Ubuntu root directory at `\\wsl$\Ubuntu`. 

Your personal files will typically be stored at:
`\\wsl$\Ubuntu\home\<yourname>`

## Map A Network Drive [OPTIONAL]
You can mount a network drive to `\\wsl$\Ubuntu` by opening `\\wsl$\` in File Explorer, right clicking the Ubuntu folder, and choosing **Map network drive…**

![alt text](image-6.png)
 
## Access Windows Files From Linux

> NOTE: Accessing Windows files from Linux is considerably slower than using the native Linux file system. Where possible, create projects within the Linux file space, typically within your home folder (/home/<yourname>/ or ~).

## Installing Applications

Always remember you’re running **two** operating systems. They may be highly integrated, but there are situations when you want an application installed in one or both.
It may be practical to use Git from either Windows or Linux. The Windows edition is installed by downloading an executable (or chocolatey), but Git on Ubuntu is installed using:

```bash
sudo apt-get update
sudo apt-get install git-all
```

Execute both commands in the Ubuntu console to install git.

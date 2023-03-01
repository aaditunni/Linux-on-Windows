# Linux-on-Windows

## Run Linux commands on Windows

Whenever I tried to do anything AWS related, I always faced the issue when it comes to running commands on my local machine. Most instructions out there are commands for Linux or Mac based systems and me having a Windows based system finds it hard to get them done.

I always wondered if I would be able to run Linux commands in my Windows environment without actually having a separate Linux OS set up.

Follow these instructions to Install Linux on Windows with WSL.

Developers can access the power of both Windows and Linux at the same time on a Windows machine. The Windows Subsystem for Linux (WSL) lets developers install a Linux distribution (such as Ubuntu, OpenSUSE, Kali, Debian, Arch Linux, etc) and use Linux applications, utilities, and Bash command-line tools directly on Windows, unmodified, without the overhead of a traditional virtual machine or dual boot setup.

You must be running Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11 to use the commands below. If you are on earlier versions, scroll down for manual installation. To check your version and build number, select Windows logo key + R, type winver, select OK.

- Open PowerShell or Command Prompt in Administrator mode and run:
    ```
        wsl --install
    ```
- By default, the installed Linux distribution will be Ubuntu. This can be changed using the -d flag.
- To change the distribution installed, enter: 
    ```
        wsl --install -d Distribution Name
    ```
- Replace Distribution Name with the name of the distribution you would like to install. 
- To see a list of available Linux distributions available for download through the online store, enter: 
    ```
        wsl --list --online
    ```

Manual installation steps for older versions of WSL
- Open PowerShell or Command Prompt in Administrator mode and run:
    ```
        dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
    ```
- To download Ubuntu 20.04:
    ```
        Invoke-WebRequest -Uri https://aka.ms/wslubuntu2004 -OutFile Ubuntu.appx -UseBasicParsing
    ```
- Or you can go to the Microsoft store and search for the desired distribution and install it it manually through the store instead of this.
- Once done, run (change app_name with the name of your Linux distribution):
    ```
        Add-AppxPackage .\app_name.appx
    ```

- If you want, you can install Windows terminal from the Microsoft Store. Using Windows Terminal enables you to open multiple tabs or window panes to display and quickly switch between multiple Linux distributions or other command lines (PowerShell, Command Prompt, Azure CLI, etc). This is the easiest way to use the Linux terminal else you'll have to go to the directory where the Linux is installed, open it and Launch the terminal through that. it's a hectic process.

- Search \\WSL$ in the path area on your file explorer and it will open the directory of your Linux.
- Access windows files on Linux:
    ```
        cd /mnt
    ```
- This way you can access files on your Windows system and run Linux commands on your Windows system and the files in in it.

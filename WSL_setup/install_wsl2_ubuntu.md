## Setting up WSL2 and Ubuntu 22.04 on Windows 11:

### Requirements:

* Windows 11. You may try on Windows 10 but it is very hit and miss: [Requirements](https://learn.microsoft.com/en-us/windows/wsl/install).

### WSL2 and Ubuntu 22.04 install:

First install Windows Terminal from the Microsoft Store:
![](resources/terminal.png)

Install WSL2 using powershell:

    wsl --install

Navigate back to the Microsoft Store and install Ubuntu 22.04 LTS

![](resources/ubuntu.png)

The dropdown menu in Windows Terminal should now have Ubuntu as an option (you make have to close and reopen):

![](resources/powershell.png)

Click this and WSL will begin the installation process. Following this Ubuntu 22.04 will be set up.

Please make sure to update regularly:

    sudo apt update
    sudo apt upgrade

### FYI
* Get used to using the command line/terminal, this is where you will be debugging. 
* **sudo** gives root (admin) privileges to a command
* **apt** is a package manager 

### Next
* Return to the [README](README.md) to continue your METR4202 setup journey

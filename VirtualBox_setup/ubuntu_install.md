### Install Ubuntu

Follow these steps to install Ubuntu 22.04 on your new VM.

Click `Start` to start the VM:

![Install Ubuntu step 1](resources/VB_install01.png)

You should be presented with the following screen (provided that you have attached the installation ISO when creating the VM - if you didn't you can add it under `Settings -> Storage -> Disk` - you will need to link it to the ISO file).
Press `Enter` with `*Try or Install Ubuntu` selected.

![Install Ubuntu step 2](resources/VB_install02.png)

This will start the installation:

![Install Ubuntu step 3](resources/VB_install03.png)

Click `Install Ubuntu`:

![Install Ubuntu step 4](resources/VB_install04.png)

Choose the keyboard layout and click `Continue`:

![Install Ubuntu step 5](resources/VB_install05.png)

Choose `Normal installation`, tick `Download updates...` and `Install third-party...` and `Continue`:

![Install Ubuntu step 6](resources/VB_install06.png)

Choose `Erase disk and install Ubuntu` and click `Install Now`:

![Install Ubuntu step 7](resources/VB_install07.png)

Confirm the changes to the disk and `Continue`:

![Install Ubuntu step 8](resources/VB_install08.png)

Choose your timezone and `Continue`:

![Install Ubuntu step 9](resources/VB_install09.png)

Fill in all the fields and `Continue`:

![Install Ubuntu step 10](resources/VB_install10.png)

This will start the installation:

![Install Ubuntu step 11](resources/VB_install11.png)

Once done, you will be prompted to restart:

![Install Ubuntu step 12](resources/VB_install12.png)

Just press `Enter`:

![Install Ubuntu step 13](resources/VB_install13.png)

After the restart, the Ubuntu should start. Skip the Online Accounts setup:

![Install Ubuntu step 14](resources/VB_install14.png)

Open the Terminal:

![Install Ubuntu step 15](resources/VB_install15.png)

And update the system using the following commands (you will be prompted for the password - it's the password that you created during the Ubuntu installation):

    sudo apt update
    sudo apt upgrade
    sudo apt autoremove


![Install Ubuntu step 16](resources/VB_install16.png)

Next install some packages needed for the next step:

    sudo apt install build-essential gcc make perl dkms

![Install Ubuntu step 17](resources/VB_install17.png)

From the menu select `Devices -> Insert Guest Additions CD image...`

![Install Ubuntu step 18](resources/VB_install18.png)

In the terminal, go the Guest Additions install folder. Use the `username` that you created during the installation (in my case it is `peter`):

    cd /media/<username>/VBox_GAs_7.0.8/
    ls

You should now see all the installation files:

![Install Ubuntu step 19](resources/VB_install19.png)


Run the `VBoxLinuxAdditions.run` (don't forget to use `sudo` - otherwise you will get an error message complaining that the program must be run with administrator privileges.):

    sudo ./VBoxLinuxAdditions.run
    
Now restart the system with the following command:

    sudo shutdown -r now

![Install Ubuntu step 20](resources/VB_install20.png)

After the restart, you should be able to resize the screen by resizing the VirtualBox window:

![Install Ubuntu step 21](resources/VB_install21.png)
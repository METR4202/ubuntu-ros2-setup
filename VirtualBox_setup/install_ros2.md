## Install ROS2 Humble

To install the ROS2, follow the instructions from the ROS website: [https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)
(just copy & paste the commands to the terminal):

![Install ROS2 step 1](resources/ros_install0.png)

Here are the steps as of now, but it may be safer to follow the ROS website in case there are updates:

    locale  # check for UTF-8

    sudo apt update && sudo apt install locales
    sudo locale-gen en_US en_US.UTF-8
    sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
    export LANG=en_US.UTF-8
    
    locale  # verify settings


Enable Universe repository:

    sudo apt install software-properties-common
    sudo add-apt-repository universe

Add the GPG key and ROS2 source:

    sudo apt update && sudo apt install curl -y
    sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

Now install ROS2:

    sudo apt update
    sudo apt install ros-humble-desktop
    sudo apt install ros-dev-tools

And test the installation - you will need 2 terminal windows (press `Ctr+Shift+N` to open the second window).
In the first terminal type:

    source /opt/ros/humble/setup.bash
    ros2 run demo_nodes_cpp talker

In the second terminal type:

    source /opt/ros/humble/setup.bash
    ros2 run demo_nodes_py listener

You should now see the following:

![Install ROS2 step 2](resources/ros_install04.png)

The talker is publishing `Hello world` messages and the listener is receiving them.

Rather than running the line `source /opt/ros/humble/setup.bash` every time you open a new terminal, you can add it to your .bashrc file.
Open the file in your favourite editor (e.g. Vim or gedit):

    gedit ~/.bashrc

and add that line at the end of the file. Now it will be automatically sourced every time you open a new terminal.
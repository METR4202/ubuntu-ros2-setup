# ROS2 Command

### ros2 run

To run a package, use `ros2 run`. Use `tab tab` to see the list of options for both package and executable.

    ros2 run <package_name> <executable_name>

    #e.g.:
    ros2 run demo_nodes_cpp talker

To have multiple instances of the same executable running in parallel, change the name of the node using `--ros-args --remap __node:=different_name`:

    ros2 run  demo_nodes_cpp talker --ros-args --remap __node:=talker2

### ros2 node

To list all the running nodes use:

    ros2 node list

To see more information about a node use (the node needs to be running - i.e. the previous command must list it):

    ros2 node info /talker

### ros2 pkg

To create a new package use:

    ros2 pkg create new_package_name


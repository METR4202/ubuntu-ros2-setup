# ROS2 Commands

All `ros2` commands can be found via `ros2 --help` from the command line. Below are a list of the most common ones that will likely come in handy.

Note that `--help` can generally be used after any command to print the usage information.

### ros2 run

To run a ROS node, use `ros2 run`. Use `tab tab` to see the list of options for both package and node.

    ros2 run <package_name> <node_name>

    # e.g.:
    ros2 run demo_nodes_cpp talker

To have multiple instances of the same node running in parallel, change the name of the node using `--ros-args --remap __node:=different_name`:

    ros2 run  demo_nodes_cpp talker --ros-args --remap __node:=talker2

### ros2 launch

A ROS launch file can be created to run multiple nodes and can also set parameters or namespace groupings for these nodes.

    ros2 launch <package_name> <launch_file_name>

Launch files will have either a `.launch` extension or are by convention named with a `_launch.py` suffix if written as a python script.

### ros2 topic

To list all the topics currently being published or subscribed to use:

    ros2 topic list

To see more information about a topic use:

    ros2 topic info <topic_name>

    # e.g.:
    ros2 topic info /chatter

To see what the topic is publishing use:

    ros2 topic echo <topic_name>

    # e.g.:
    ros2 topic echo /chatter

### ros2 node

To list all the running nodes use:

    ros2 node list

To see more information about a node use:

    ros2 node info <node_name>
    
    # e.g.:
    ros2 node info /talker

 Note that the node needs to be running, i.e. the previous command must list it.

### ros2 pkg

To create a new package use:

    ros2 pkg create new_package_name


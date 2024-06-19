# Colcon Command

ROS2 uses `colcon` as a build system.

To enable the autocomplete for colcon commands add the `colcon-argcomplete.bash` to your `.bashrc` (or just source it):

    echo 'source /usr/share/colcon_argcompete/hook/colcon-argcomplete.bash' >> ~/.bashrc

To build the workspace use `colcon build` from the root dir of the workspace (e.g. `ros2_ws`). This will build all the package present in the `src` directory:

    cd ~/ros2_ws
    colcon build

To build a specific package use `--packages-select`:

    colcon build --packages-select m4202_py_pkg

You need to build the package after every change.

To have ros2 run the executable from the `src` directory rather than the `install` directory, run the build with `--symlink-install`.
You will also need to make the source file executable by adding the shebang (`#!/usr/bin/env python3`) line at the start of the file and adding executable permissions:

    chmod +x src/m4202_py_pkg/m4202_py_pkg/m4202_first_node.py

    colcon build --packages-select m4202_py_pkg --symlink-install

This way you can just re-run the updated node without recompiling (this only works for Python, C++ nodes need to be recompiled after every change).


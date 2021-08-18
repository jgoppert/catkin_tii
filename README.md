# purt_catkin_ws
PURT catkin workspace

## Setup

### Before you build
1. Make sure you have ROS noetic installed
2. Make sure your .bashrc only contains the following line for sourcing ros:

```bash
. /opt/ros/noetic/setup.bash

```

### Building

```bash
mkdir -p ~/git
cd ~/git
git clone https://github.com/jgoppert/purt_catkin_ws.git
cd purt_catkin_ws
git submodule update --init --recursive
./src/PX4-Autopilot/Tools/setup/ubuntu.sh 
```

Reboot computer

```bash
sudo apt install python3-catkin-tools ros-noetic-geographic-msgs ros-noetic-mavlink libgeographic-dev libignition-commond3-graphics-dev xterm
cd ~/git/purt_catkin_ws
catkin build
. ./devel/setup.bash
```

Install geographiclib datasets

```bash
cd ~/git/purt_catkin_ws/src/mavros/mavros/scripts
./install_geographiclib_datasets.sh
```

### Troubleshooting

1. If PX4 is stuck building cmake, make sure you have run:
```bash
git submodule update --init --recursive
```
and that it completes successfully.

## Run

After the system is built, run:

```bash
cd ~/git/purt_catkin_ws
. ./devel/setup.bash
roslaunch qualisys abu_dhabi.launch
```

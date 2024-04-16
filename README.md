# Simple TopoSLAM model

The `simple_toposlam_model` repository provides a simple implementation of topological SLAM concept.

## Prerequisites:
- [ROS](https://ros.org) Melodic or Noetic
- For simulated demo: [habitat-sim v0.1.7](https://github.com/facebookresearch/habitat-sim/tree/v0.1.7), [habitat-lab v0.1.7](https://github.com/facebookresearch/habitat-lab/tree/v0.1.7), and [ROS tools for Habitat](https://github.com/cnndepth/habitat_ros)

## Installation
After installing ROS and OpenPlaceRecognition, build simple_toposlam_model as ROS package:
```
cd your_ros_workspace/src
git clone https://github.com/KirillMouraviev/PRISM-TopoMap
cd ../..
catkin_make
```

After that, download the actual [weights](https://drive.google.com/file/d/1r4Nw0YqHC9PKiZXDmUAWZkOTvgporPnS/view?usp=sharing) for the place recognition model] and set correct path to the weights in the config files `habitat_mp3d.yaml` and `husky_rosbag.yaml`.

## Launch

We provide the launch script for Habitat simulator v0.1.7 and Matterport 3D dataset. The example can be run as follows:


Terminal 1
```
roscore
```

Terminal 2
```
sudo -s
<source ROS and Habitat ros workspace>
roslaunch habitat_ros toposlam_experiment_mp3d_4x90.launch
```

Terminal 3
```
cd your_ros_workspace
source devel/setup.bash
roslaunch simple_toposlam_model build_map_by_iou.launch scene_name:=<scene name>
```

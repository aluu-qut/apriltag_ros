# 1. apriltags_ros: AL additions

modified 2021/02/09

## 1.1. ros catkin_make compilation
for `apriltags_ros` to compile with `catkin_make` and not `catkin_make_isolated`, need to build and install the apriltags library, found [here](https://github.com/aluu-qut/apriltag).

the installation instructions are [here](https://github.com/aluu-qut/apriltag#install).

```
cd apriltag
mkdir build
cd build
cmake ../
sudo make install
```

the apriltags folder can be deleted now

`apriltags_ros` developers have already made tutorials to use their launch files, find the Continuous video tutorial [here](http://wiki.ros.org/apriltag_ros/Tutorials/Detection%20in%20a%20video%20stream).

## 1.2. apriltag_ros configuration

### 1.2.1. topic links to realsense2_camera

in `apriltag_ros/launch/continuous_detetion.launch` file, changed `camera_name` and `image_topic` names to `/camera/color` and `image_rect_color` respectively. found those topic names through `rostopic list` and found what the realsense2_camera publishes


### 1.2.2. tag id and size config


in `apriltags_ros/config/settings.yaml` file, updated tag_family to match the printed tag i currently had which was `tag16h5`. left other settings the default, and the previously linked tutorial gives more details for other settings.

in `apriltags_ros/config/tags.yaml` file, added the tag id number and physically measured side length size under `standalone_tags` section.


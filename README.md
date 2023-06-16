# UR3 Berry Harvesting Integration

This repository showcases the integration of various technologies, including the UR3 robotic arm, Intel D435F camera, custom-made gripper, and other components for berry harvesting applications. The goal of this project is to develop a robust system that can detect berries, determine their pose, and execute precise gripping and harvesting actions using the UR3 arm.

## :wrench: Technologies Used

The integration project utilizes the following technologies:

- ROS (Robot Operating System) - Noetic version
- RViz - 3D visualization tool for ROS
- RQt - GUI framework for ROS
- ddynamic_reconfigure - Dynamic reconfiguration for ROS
- realsense-ros - ROS packages for Intel RealSense cameras
- aruco_ros - ROS wrapper for ArUco markers


## :file_folder: Project Structure

The workspace structure for the UR3 Berry Harvesting Integration project is as follows:

```
cam_ws/
├── build/
├── devel/
└── src/
│ ├── aruco_ros/
│ ├── realsense-ros/
│ ├── ddynamic_reconfigure/
└── ...
```



- `ur3_ws`: This workspace contains the UR3-specific packages and dependencies required for the robotic arm integration. It includes packages like `universal_robots_ros_driver` and `universal_robot`.

- `cam_ws`: This workspace focuses on camera-related packages and dependencies. It includes packages like `realsense-ros` and `ddynamic_reconfigure`.

## :rocket: Getting Started

To start the integration system, follow these steps:

1. Launch the camera:
```
roslaunch realsense2_camera rs_camera.launch
```

2. Launch the aruco_ros node to detect the identifiable objects:

```
roslaunch aruco_ros single.launch
```

3. Launch the RViz visualization tool using the `example_rviz.launch` file:

```
roslaunch ur_robot_driver example_rviz.launch
```
4. Start the UR3 robot using the ur3_bringup.launch file:
```
roslaunch ur_robot_driver ur3_bringup.launch robot_ip:=<YOUR_ROBOT_IP>
```
5. Run the real_controller_examples.py script to control the vision system, calculate the pose, and execute other relevant actions:
```
rosrun ur_control real_controller_examples.py
```
Ensure that you have correctly configured the IP address of your UR3 robot in the launch file.

## 🐳 Dockerfile

To simplify the setup process, a Dockerfile is provided in the repository. The Dockerfile sets up the necessary environment and installs the required ROS packages and dependencies. It can be used to create a Docker image that encapsulates the entire project's workspace.

## 🙏 **Acknowledgements**

This project acknowledges the valuable resources and guidance provided by the following tools and repositories:

- [ddynamic_reconfigure](https://github.com/pal-robotics/ddynamic_reconfigure) - Dynamic reconfiguration for ROS
- [realsense-ros](https://github.com/IntelRealSense/realsense-ros) - ROS packages for Intel RealSense cameras
- [aruco_ros](https://github.com/pal-robotics/aruco_ros) - ROS wrapper for ArUco markers

For more information on how to integrate the UR3 arm with the camera system and perform berry harvesting tasks, please refer to the provided scripts and documentation in the repository.

## 📧 **Contact Information**

For any questions or further inquiries, please feel free to contact me at jair2000.0224@hotmail.com.

## 📃 **License**

This project is licensed under the terms of the MIT License. Feel free to use, modify, and distribute the code, keeping in mind the attribution and licensing requirements.

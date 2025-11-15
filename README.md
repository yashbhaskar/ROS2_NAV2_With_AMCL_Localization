# ROS2_NAV2_With_AMCL_Localization
This repo contains ROS 2 packages for complete autonomous navigation. The first package includes robot URDF model with Gazebo simulation, sensors and plugins. The second package provides Nav2-based autonomous navigation and AMCL localization with a custom launch file that integrates bringup_launch.py for navigation, localization, and map handling.

---

## 📍 AMCL Localization

**AMCL (Adaptive Monte Carlo Localization)** is a probabilistic algorithm used in ROS 2 to determine the robot’s precise position (x, y, θ) on a known map. It uses a particle filter approach where multiple pose hypotheses (particles) are sampled and continuously updated. AMCL compares real-time LiDAR scan data with the pre-built map and incorporates wheel odometry to refine pose estimates. Over time, particles converge to the most likely robot pose, enabling reliable and accurate localization even with noise or sensor uncertainty.
This accurate pose estimation is essential for Nav2 path planning, collision-free navigation, recovery behaviors, and stable goal execution in autonomous robots.

<img width="1847" height="1047" alt="1111" src="https://github.com/user-attachments/assets/8cb916f6-d31f-42d8-ad21-fb8d6cf5c7a8" />


---

## 🌟 Features

- Complete robot URDF/XACRO model with sensors and gazebo integration
- Nav2-based autonomous navigation and AMCL localization support
- Custom bringup launch integrating navigation, localization and RViz
- Support for 2D LiDAR, IMU and differential drive odometry
- Real-time map loading, planning and goal execution
- RViz visualization with navigation plugins
- Map loading for localization workflows
- Modular package structure for easy customization and extension

---

## 🎯 Learning Objectives

- Understand robot description using URDF/XACRO and sensor configuration
- Learn Gazebo simulation with realistic sensor plugins
- Perform autonomous navigation using the Nav2 framework
- Implement AMCL localization on a known static map
- Configure and launch Nav2 bringup pipelines
- Visualize robot state, TF frames, paths and sensors in RViz
- Experiment with navigation parameters, recovery behavior and maps

---

## Installation

### Make Workspace
```bash
mkdir robot_ws/
```

### Change Workspace
```bash
cd robot_ws
```

### Make src
```bash
mkdir src/
```

### Change Workspace
```bash
cd src
```

### Clone This Repository
```bash
git clone https://github.com/yashbhaskar/ROS2_NAV2_With_AMCL_Localization.git
```

### Install Nav2
```bash
sudo apt update
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-nav2-bringup
```

### (Optional recommended packages)
```bash
sudo apt install ros-humble-nav2-common
sudo apt install ros-humble-nav2-map-server
sudo apt install ros-humble-nav2-behavior-tree
```

### Change Workspace
```bash
cd ..
```

### Build the Package
```bash
colcon build --packages-select my_bot robot_navigation
source install/setup.bash
```

---

## 🚀 How to Run

### 1st Terminal : Launch robot in gazebo
```bash
ros2 launch my_bot gazebo.launch.py
```

### 2nd Terminal : Start autonoumous navigation
```bash
ros2 launch robot_navigation amcl_localization.launch.py
```
- Now rviz is open and robot is shown in white colour now use 2D Pose Estimate to set the robot’s initial pose on the map and start AMCL localization.
- Then use Nav2 Goal / 2D Goal Pose to send a navigation goal. The robot will autonomously plan a path and move toward the target, avoiding obstacles and reaching the goal successfully.
- You may notice slight odometry drift or small pose adjustments, which is normal during AMCL convergence as the particle filter refines the robot’s exact position.

<img width="1847" height="1047" alt="2222" src="https://github.com/user-attachments/assets/13ddf718-86bc-4837-b982-c087033b8c81" />


---

## ✉️ Contact

📧 Yash Bhaskar – ybbhaskar19@gmail.com

📌 GitHub: https://github.com/yashbhaskar


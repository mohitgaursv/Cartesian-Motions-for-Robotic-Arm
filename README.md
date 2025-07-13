# Cartesian-Motions-for-Robotic-Arm
Motions for Robotic Arm 
Summary of What We’ve Done So Far
1. Selected Robot
Chose UR10e, a widely supported 6-DOF collaborative robot arm with publicly available URDF and ROS 2 packages.

2. Cloned UR10e ROS 2 Repositories
Inside your ROS 2 workspace source folder (~/ur10_ws/src), we cloned these repos to get robot description, drivers, bringup, and controllers:

bash
Copy
Edit
cd ~/ur10_ws/src

git clone -b humble https://github.com/UniversalRobots/Universal_Robots_ROS2_Description.git
git clone -b humble https://github.com/UniversalRobots/Universal_Robots_ROS2_Driver.git
git clone -b humble https://github.com/UniversalRobots/Universal_Robots_ROS2_Bringup.git
git clone -b humble https://github.com/UniversalRobots/Universal_Robots_ROS2_Controllers.git
Description: URDF, meshes, robot model

Driver: Interface with real or simulated robot hardware

Bringup: Launch files to bring the robot and controllers up

Controllers: Joint trajectory controllers and interfaces

3. Installed Dependencies and Built Workspace
From the workspace root (~/ur10_ws):

bash
Copy
Edit
rosdep install --from-paths src --ignore-src -r -y
colcon build --event-handlers console_direct+ --parallel-workers 1
source install/setup.bash
This installed required ROS 2 dependencies and built the entire workspace.

4. Launched UR10e in Ignition Gazebo Simulation
Run the launch file with dummy robot IP to avoid real robot connection error:

bash
Copy
Edit
ros2 launch ur_bringup ur10e.launch.py ign:=true robot_ip:=0.0.0.0
Spawned UR10e robot model in Ignition Gazebo simulator.

Started controllers for simulated robot motion.

5. Purpose Achieved So Far
Set up a fully functional simulation environment with ROS 2 and Ignition Gazebo.

Visualized the UR10e robot in a simulated world ready for motion control.

Created a foundation to implement smooth Cartesian end-effector motion and advanced trajectory planning.


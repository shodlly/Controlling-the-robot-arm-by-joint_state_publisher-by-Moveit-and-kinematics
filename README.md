

# Robot Arm Control using Joint State Publisher and MoveIt with Kinematics

This repository guides the control of a robot arm using ROS tools like `joint_state_publisher` and MoveIt. It covers environment setup, workspace creation, dependency installation, and advanced motion planning with simulation in Gazebo.

## Reference Repository

The setup described here is based on the [arduino_robot_arm repository](https://github.com/smart-methods/arduino_robot_arm.git).

## Setup Environment

- **Operating System**: Ubuntu 20.04
- **ROS Version**: ROS 1 Noetic

### Requirements

#### Create a Workspace

1. **Source ROS Environment:**

    ```sh
    source /opt/ros/noetic/setup.bash
    ```

2. **Create a Catkin Workspace:**

    ```sh
    mkdir -p ~/catkin_ws/src
    ```

3. **Build the Workspace:**

    ```sh
    cd ~/catkin_ws/
    catkin_make
    ```

4. **Source the Workspace Setup:**

    ```sh
    source devel/setup.bash
    ```

5. **Verify ROS Package Path:**

    ```sh
    cd ~/catkin_ws/src
    sudo apt install https://github.com/smart-methods/arduino_robot_arm
    ```

6. **Add the `arduino_robot_arm` Package to `src`:**

    ```sh
    cd ~/catkin_ws
    rosdep install --from-paths src --ignore-src -r -y
    sudo apt-get install ros-noetic-moveit
    sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
    sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
    sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
    ```

### Install Dependencies

1. **Install All Required Dependencies:**

    ```sh
    cd ~/catkin_ws
    rosdep install --from-paths src --ignore-src -r -y
    sudo apt-get install ros-noetic-moveit
    sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
    sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
    sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
    ```

2. **Build the Workspace Again:**

    ```sh
    catkin_make
    ```

## Controlling the Robot Arm

### Using Joint State Publisher

1. **Install `robot_state_publisher`:**

    ```sh
    sudo apt-get install ros-noetic-robot-state-publisher
    ```

2. **Launch Motor Checking Node:**

    ```sh
    roslaunch robot_arm_pkg check_motors.launch
    ```
![image](https://github.com/user-attachments/assets/a2271d8f-6c75-4567-86b7-e8e13528159e)

3. **Launch Motor Checking in Gazebo:**

    ```sh
    roslaunch robot_arm_pkg check_motors_gazebo.launch
    ```
![image](https://github.com/user-attachments/assets/becdd974-fa0d-4ccd-b707-7bdf04d91c3c)

### Using MoveIt and Kinematics

1. **Launch MoveIt Demo:**

    ```sh
    roslaunch moveit_pkg demo.launch
    ```
![image](https://github.com/user-attachments/assets/59dd9a34-0841-43c7-84f0-3d3193a0a03c)

## Conclusion

This repository offers a structured approach to controlling a robot arm using ROS tools. By following the instructions, users can set up their environment, build a Catkin workspace, and leverage `joint_state_publisher` and MoveIt for advanced control and simulation. This comprehensive guide provides the foundation for effective robot arm manipulation and simulation in ROS.

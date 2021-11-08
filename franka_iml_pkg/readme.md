### Versions 

- FCI (system) OS version - 4.04 (Check in franka Dashboard settings) 
- Libfranka version 0.7.0 
- Franka_ros (noetic devel) 
- realsense2 


### New User
If you create a new user login in the lab PC. You will need to do the following steps (only one time). 

```bash
$ echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
$ sudo addgroup realtime
$ sudo usermod -a -G realtime $(whoami)
```

Restart the PC. 

*These commands will add noetic to setup path, and give permission to this new user to use realtime kernel to interact with Franka Panda.*

### How to compile 

Create a workspace, git clone the repo, catkin make the packges

```bash
$ mkdir -p catkin_ws/src
$ cd catkin_ws/src 
$ git clone -b noetic-devel 
$ cd ..
$ catkin_make 
```

### How to run 

The following launch file will run joint trajectory position controller, state controller, MoveIt (that connects to joint trajectory position controller), gripper (if load_gripper:=true is passed), realsense camera (if load_camera:=true is passed). 

```bash
$ roslaunch franka_iml_pkg franka_bringup.launch
```

### Suggestions

If you want to add anything manually in the franka URDF or moveit, please either make a new branch or fork this repository. 
This is a general repository that should work and help for everyone in IML lab. 

Thank you 







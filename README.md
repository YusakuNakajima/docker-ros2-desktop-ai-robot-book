## コマンド
- 
- ` vcs import src < src/underlay.rosinstall`
- `rosdep install -r --from-paths src --ignore-src --rosdistro $ROS_DISTRO -y`
- `colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release`
    - clean cache option `--cmake-clean-cache`
## PC内環境でのURデモコマンド
demo1
```
ros2 launch ur_bringup ur_control.launch.py ur_type:=ur5e robot_ip:=192.168.56.42 use_fake_hardware:=true launch_rviz:=true
ros2 launch ur_bringup test_joint_trajectory_controller.launch.py
```
demo2
```
ros2 launch ur_bringup ur_control.launch.py ur_type:=ur5e robot_ip:=192.168.56.42 robot_controller:=scaled_joint_trajectory_controller use_fake_hardware:=true launch_rviz:=true
ros2 launch ur_bringup test_scaled_joint_trajectory_controller.launch.py
```
moveit demo
```
ros2 launch ur_bringup ur_control.launch.py ur_type:=ur5e robot_ip:=192.168.56.42 use_fake_hardware:=true launch_rviz:=false
ros2 launch ur_bringup ur_moveit.launch.py ur_type:=ur5e robot_ip:="192.168.56.42" use_fake_hardware:=true launch_rviz:=true
```
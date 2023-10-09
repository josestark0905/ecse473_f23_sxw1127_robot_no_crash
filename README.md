# ecse473_f23_sxw1127_robot_no_crash
## Build
1. Download this package into the catkin workspace, for example `~/catkin_ws`
2. Change into the catkin workspace directory, for example `cd ~/catkin_ws`
3. Build the package by simply `catkin_make`
4. Source with `source devel/setup.bash`
## Launch by default
### Argument
'wall_dist_set': `false` by default, which means the wall_dist uses the default value 1
### Launch with default parameter `wall_dist = 1`
`roslaunch robot_no_crash robot_supervisor.launch`
### Launch with reload parameter `wall_dist = 0.5`
`roslaunch robot_no_crash robot_supervisor.launch wall_dist_set:=true`


# ecse473_f23_sxw1127_robot_no_crash
## Build
1. Download this package into the catkin workspace, for example `~/catkin_ws`
2. Change into the catkin workspace directory, for example `cd ~/catkin_ws`
3. Build the package by `catkin_make`
4. Source with `source devel/setup.bash`

## Launch by default
### Argument
1. `wall_dist_set`: `false` by default, which means the parameter `wall_dist` uses the default value 1, set it to `true` can reload the parameter `wall_dist` to 0.5
### Launch with default parameter `wall_dist = 1`
`roslaunch robot_no_crash launch_by_default.launch`
### Launch with reload parameter `wall_dist = 0.5`
`roslaunch robot_no_crash launch_by_default.launch wall_dist_set:=true`
### Use stdr_launchers to view robot
The stdr_launchers of a map with a default robot0 will be turned on automatically
### Use rqt_gui to control robot
The rqt_gui will be turned on automatically, the twist topic of Robot Steering needs to be set to `/robot0/des_del`

## Launch multiple robots with specify namespace
### Argument
1. `wall_dist_set`: `false` by default, which means the parameter `wall_dist` uses the default value 1, set it to `true` can reload the parameter `wall_dist` to 0.5
2. `robot_ns`: `robot0` by default, which means the default namespace is `robot0`.
### Launch with default namespace robot0
`roslaunch robot_no_crash robot_supervisor.launch`
### Launch with specify namespace, such as robot1
`roslaunch robot_no_crash robot_supervisor.launch robot_ns:=robot1`
### Use stdr_launchers to view robot
1. `roslaunch stdr_launchers server_with_map_and_gui.launch`
2. Only the map will be turned on, robots need to be added from gui
3. The robot will run automatically if the namespace is the same as started robot node. For example, robot1 will run automatically if `roslaunch robot_no_crash robot_supervisor.launch robot_ns:=robot1` is used
### Use rqt_gui to control robot
1. Start the rqt_gui with `rosrun rqt_gui rqt_gui`
2. The twist topic of Robot Steering needs to be set to `/<namespace>/des_del`


# replace     
replace tow file( arm_controller.cpp ,  arm_controller.h )  at /open_manipulator/open_manipulator_position_ctrl  

# run   
roscore   
roslaunch open_manipulator_gazebo open_manipulator_gazebo.launch   
roslaunch open_manipulator_moveit open_manipulator_demo.launch use_gazebo:=true   
rostopic pub /measure std_msgs/String "test" --once   

you can get KinematicsPos which you want point like below format  

ROS_INFO("Pose Reference Frame = %.3f,%.3f,%.3f _  %.3f,%.3f,%.3f,%.3f",\
	res.kinematics_pose.pose.position.x, res.kinematics_pose.pose.position.y, res.kinematics_pose.pose.position.z,\
	res.kinematics_pose.pose.orientation.x, res.kinematics_pose.pose.orientation.y, res.kinematics_pose.pose.orientation.z, res.kinematics_pose.pose.orientation.w);



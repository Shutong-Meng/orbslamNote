# orbslamNote
Some Notes of using ORB_SLAM2

测试双目Euroc数据集(ros)  
roscore  
rosrun ORB_SLAM2 Stereo Vocabulary/ORBvoc.txt Examples/Stereo/EuRoC.yaml true   
rosbag play ~/Downloads/V1_01_easy.bag /cam0/image_raw:=/camera/left/image_raw /cam1/image_raw:=/camera/right/image_raw  



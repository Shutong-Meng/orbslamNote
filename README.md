# orbslamNote
Some Notes of using ORB_SLAM2

**测试双目Euroc数据集(ros)

  roscore  
  rosrun ORB_SLAM2 Stereo Vocabulary/ORBvoc.txt Examples/Stereo/EuRoC.yaml true   
  rosbag play ~/Downloads/V1_01_easy.bag /cam0/image_raw:=/camera/left/image_raw /cam1/image_raw:=/camera/right/image_raw  


**关于四元数(quaternion)  

旋转矩阵冗余，欧拉旋转会存在万向锁问题。  

在数学上，quaternion表示复数w+xi+yj+zk，其中i,j,k都是虚数单位：  
  i*i = j*j = k*k= -1  
  i*j = k, j*i = -k  
quaternion可以记为[w,V]或[w,(x,y,z)]  

要表示以向量N为轴，轴旋α度,相对的quaternion应该是：  
  q =[cos(α/ 2), sin(α/ 2)N]  
    =[cos(α/ 2), (sin(α/ 2)Nx, sin(α/ 2)Ny, sin(α/ 2)Nz)]  
一般Ｎ为单位向量，方便计算。
 
为了对3D空间中的一个点p(x,y,z)进行旋转，需要先把它转换为quaternion形式p=[0, (x,y,z)]。  
定义q=[cos(α/ 2), sin(α/ 2)N]为旋转quaternion，这里N为单位矢量长度的旋转轴，α为旋转角度。那么旋转之后的点p’则为:  
p’ = qpq-1

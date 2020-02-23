# LSD-SLAM-with-ubuntu1804-and-melodic
# LSD-SLAM-with-ubuntu1804-and-melodic

I changed some code to use the a more recent g2o,so you need to clone or download my code.

note：EIGEN 3.2.* 

1.
sudo apt-get install python-rosinstall
mkdir ~/rosbuild_ws
cd ~/rosbuild_ws
rosws init . /opt/ros/melodic
mkdir package_dir
rosws set ~/rosbuild_ws/package_dir -t .
echo "source ~/rosbuild_ws/setup.bash" >> ~/.bashrc
bash
cd package_dir

2.
install some dependency:
sudo apt-get install ros-melodic-libg2o ros-melodic-cv-bridge liblapack-dev libblas-dev freeglut3-dev libsuitesparse-dev libx11-dev

sudo apt install libqglviewer-dev-qt4
cd /usr/lib/x86_64-linux-gnu
sudo ln -s libQGLViewer-qt4.so libQGLViewer.so.

3.
rosmake LSD-SLA....(your file name)

4.
roscore 

5.
rosrun lsd_slam_viewer viewer

6.
rosrun lsd_slam_core live_slam image:=/image_raw camera_info:=/camera_info

7.
rosbag play ./LSD_room.bag  #you need download this .bag file in http://vmcremers8.informatik.tu-muenchen.de/lsd/LSD_room.bag.zip

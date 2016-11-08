## ROS安装步骤  
1.Setup sources.list  
`sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'`  

2.Set up keys
`sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116`  
 

3.Installation  
make sure Debian package index is up-to-date:  
`sudo apt-get update`  
![](http://p1.bpimg.com/567571/d6c8da7ff2cb1b86.png) 

Desktop-Full Install:  
`sudo apt-get install ros-jade-desktop-full`  
![](http://p1.bpimg.com/567571/4f80ffc0f0f320e1.png)

Find available packages `apt-cache search ros-jade`
![](http://p1.bpimg.com/567571/8c8d85f16dfce582.png)

4.Initialize rosdep  
`sudo rosdep init
 rosdep update`  

![](http://p1.bpimg.com/567571/40750bdb8eef9e1e.png)

5.Environment Setup  
`echo "source /opt/ros/jade/setup.bash" >> ~/.bashrcsource ~/.bashrc`  

6.Getting rosinstall  
`sudo apt-get install python-rosinstall`  

![](http://i1.piimg.com/567571/ffe56af362554fc3.png)

7.Obtain source code of the installed packages  
`$ apt-get source ros-jade-laser-pipeline`  

![](http://i1.piimg.com/567571/8a951e0dfa63942e.png)














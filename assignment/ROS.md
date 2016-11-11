## ROS安装过程

* 检查自己的Ubuntu版本

  ```
  sudo lsb_release -a
  ```

  找到Description检查自己的版本号

* 如果是Ubuntu 14.01，15.04参考

  > http://wiki.ros.org/jade/Installation/Ubuntu

  如果是Ubuntu 15.10，16.04参考

  > http://wiki.ros.org/kinetic/Installation/Ubuntu

* setup sources.list

  ```
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  ```

* set up keys

  ```
  sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
  ```

* 安装，选择Desktop-Full install

  ```
  sudo apt-get install ros-jade-desktop-full
  ```

*    To find available packages, use: 

  ```
  apt-cache search ros-jade
  ```

* Initialize rosdep

  ```
  sudo rosdep init
  resdep update
  ```

* Environment setup

  ```
  echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
  source ~/.bashrc
  ```

* Getting rosinstall

  ```
  sudo apt-get install python-rosinstall
  ```

  ​
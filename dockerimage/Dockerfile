FROM kinetic:localization

RUN apt-get update && apt-get -y upgrade

RUN cd /root/catkin_ws/src/ &&\
  git clone https://github.com/ros-perception/slam_gmapping


RUN /bin/bash -c "source /opt/ros/kinetic/setup.bash &&\
                  cd /root/catkin_ws &&\
                  source /root/catkin_ws/devel/setup.bash &&\
                  rosdep -y install gmapping &&\
                  /opt/ros/kinetic/bin/catkin_make" 

RUN apt-get -y install ros-kinetic-rtabmap ros-kinetic-rtabmap-ros 


RUN mkdir /root/.gazebo &&\
    curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C /root/.gazebo/


RUN  rm -rf /var/lib/apt/lists/*


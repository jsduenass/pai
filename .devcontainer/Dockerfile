ARG ROS_DISTRO=${ROS_DISTRO}
FROM osrf/ros:${ROS_DISTRO}-desktop-full

SHELL ["/bin/bash", "-c"]

ENV DISPLAY=:0
ENV QT_X11_NO_MITSHM=1

# Install catkin tools
RUN apt-get update && \
    apt-get install python3-catkin-tools -y

RUN echo "source /opt/ros/${ROS_DISTRO}/setup.bash" >> ~/.bashrc

# Install pip tools 
RUN apt-get install -y python3-pip

# Install pigpio python module
RUN pip3 install pigpio

# Install ros control dependencies for simulation
RUN apt-get install -y ros-${ROS_DISTRO}-ros-control ros-${ROS_DISTRO}-ros-controllers

WORKDIR /root/catkin_ws/

CMD ["bash"]

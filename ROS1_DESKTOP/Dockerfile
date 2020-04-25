FROM ubuntu:latest

# Set up mirrors
RUN apt-get update \
    &&  apt-get install -y \
    lsb-release \
    gnupg \
    && sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) \
    main" > /etc/apt/sources.list.d/ros-latest.list' \
    && apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key \
    C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

# Install required packages
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    wget \
    python3-pip \
    ros-melodic-desktop-full \
    ros-melodic-openni* \
    python-rosdep \
    python-rosinstall \
    python-rosinstall-generator \
    python-wstool \
    build-essential

# Make source persistent
RUN echo "source /opt/ros/melodic/setup.bash" >> /root/.bashrc

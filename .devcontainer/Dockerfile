# Start with jammy base image
FROM ubuntu:jammy

# Configure the CLI to be non interactive
ENV DEBIAN_FRONTEND=noninteractive

# Configure locale
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8

# Install basic tools
RUN apt-get update && apt-get install -y \
    git

# Configure ROS2 repositories
RUN apt update && apt install -y software-properties-common && add-apt-repository universe
RUN apt update && apt install -y curl gnupg lsb-release && curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" | tee /etc/apt/sources.list.d/ros2.list > /dev/null
RUN cat /etc/apt/sources.list.d/ros2.list

# Install ROS2
RUN apt update && apt -y upgrade
RUN apt install -y ros-humble-ros-base

# Create the default user for container
RUN useradd -ms /bin/bash fagging
USER faggin
WORKDIR /home/fagging/

ENV DEBIAN_FRONTEND=
CMD ["/bin/bash"]

FROM osrf/ros:jazzy-desktop

ARG USERNAME=ubuntu
ARG USER_UID=1000
ARG USER_GID=1000

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    cmake \
    git \
    python3-pip \
    python3-colcon-common-extensions \
    python3-rosdep \
    python3-vcstool \
    python3-pytest \
    sudo \
    && rm -rf /var/lib/apt/lists/* \
    && echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

ENV RMW_IMPLEMENTATION=rmw_fastrtps_cpp

USER $USERNAME
WORKDIR /home/$USERNAME

RUN mkdir -p thirdparties_ws/src && \
    cd thirdparties_ws/src && \
    git clone -b v2.4.3 https://github.com/eProsima/Micro-XRCE-DDS-Agent.git && \
    cd .. && \
    /bin/bash -c "source /opt/ros/jazzy/setup.bash && colcon build"

CMD ["bash"]

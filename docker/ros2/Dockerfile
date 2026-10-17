FROM osrf/ros:jazzy-desktop-full

RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    cmake \
    git \
    python3-pip \
    python3-colcon-common-extensions \
    python3-rosdep \
    python3-vcstool \
    python3-pytest \
    && rm -rf /var/lib/apt/lists/*

RUN if [ ! -f /etc/ros/rosdep/sources.list.d/20-default.list ]; then \
        rosdep init; \
    fi

ENV RMW_IMPLEMENTATION=rmw_fastrtps_cpp

ARG USERNAME=ros
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN if getent group $USER_GID > /dev/null 2>&1; then \
        GROUP_NAME=$(getent group $USER_GID | cut -d: -f1); \
    else \
        groupadd --gid $USER_GID $USERNAME; \
        GROUP_NAME=$USERNAME; \
    fi && \
    if id -u $USER_UID > /dev/null 2>&1; then \
        USER_NAME=$(getent passwd $USER_UID | cut -d: -f1); \
        if [ "$USER_NAME" != "$USERNAME" ]; then \
            usermod -l $USERNAME -d /home/$USERNAME -m $USER_NAME; \
        fi; \
        usermod -g $USER_GID $USERNAME; \
    else \
        useradd --uid $USER_UID --gid $GROUP_NAME -m -s /bin/bash $USERNAME; \
    fi && \
    apt-get update && apt-get install -y --no-install-recommends sudo && \
    rm -rf /var/lib/apt/lists/* && \
    echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME && \
    chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME
WORKDIR /home/$USERNAME/ws

CMD ["bash"]

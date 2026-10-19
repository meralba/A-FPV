FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

# Install essential system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    sudo \
    build-essential \
    cmake \
    python3-pip \
    && rm -rf /var/lib/apt/lists/*

# Setup non-privileged user to avoid permission issues with host volumes
ARG USERNAME=px4
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

USER $USERNAME
WORKDIR /home/$USERNAME

# Clone and build PX4 SITL directly as the non-root user (no heavy chown needed)
RUN git clone --recursive https://github.com/PX4/PX4-Autopilot.git -b v1.17.0 \
    && cd PX4-Autopilot \
    && make px4_sitl_default

WORKDIR /home/$USERNAME/PX4-Autopilot

CMD ["make", "px4_sitl", "gz_x500"]
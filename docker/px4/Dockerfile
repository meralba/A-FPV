FROM px4io/px4-dev:v1.17.0

ENV DEBIAN_FRONTEND=noninteractive

WORKDIR /home/px4

RUN git clone --recursive https://github.com/PX4/PX4-Autopilot.git -b v1.17.0 \
    && cd PX4-Autopilot \
    && bash Tools/setup/ubuntu.sh --no-nuttx \
    && make px4_sitl_default

WORKDIR /home/px4/PX4-Autopilot

CMD ["make", "px4_sitl", "gz_x500"]
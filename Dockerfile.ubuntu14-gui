#encode: utf-8
#镜像层:基于ubuntu14.04对图形库支持
#image description: Support GUI lib for which based on ubuntu14.04
FROM ansible/ubuntu14.04-ansible
MAINTAINER seafly seafly0616@qq.com

WORKDIR /root

#install GUI support for image
RUN sudo apt-get update
RUN sudo apt-get install -y xinit
RUN sudo apt-get install -y gdm lightdm --force-yes
RUN sudo apt-get install -y kubuntu-desktop

#-v "/etc/localtime:/etc/localtime:ro" -v "/tmp/.X11-unix:/tmp/.X11-unix"
ENV DISPLAY unix$DISPLAY
ENV GDK_SCALE
ENV GDK_DPI_SCALE

ENTRYPOINT ["/bin/bash"]

#Your host must allow following servers
#host:$ sudo apt-get install -y x11-xserver-utils
#host:$ xhost +

#Run container must with following args:
#host:$ sudo docker run -d ... \
#host:$     -v /etc/localtime:ro \
#host:$     -v /tmp/.X11-unix:/tmp/.X11-unix

#A complete container running example
#$ sudo apt-get install -y x11-xserver-utils
#$ xhost +
#$ sudo docker run -d -p 4096:4096 \
#       --name=container1 \
#       --net=bridge \
#       --memory=4096m \
#       --hostname=container1 \
#       -v /etc/localtime:/etc/localtime:ro \
#       -v /tmp/.X11-unix:/tmp/.X11-unix
#       -it ubuntu14:latest /bin/bash
#
# then you can run gui apps in your container

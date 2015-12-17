FROM phusion/baseimage

RUN apt-get update && apt-get install -y leafpad
#RUN apt-get install -y dbus-x11
RUN apt-get install -y xauth

#create user 'developer' belonging to 'sudo' group so that he/she can use sudo
ENV the_user developer
ENV sudo_group sudo
RUN useradd $the_user -m -s /bin/bash -G $sudo_group

ENV USER $the_user
ENV HOME /home/$the_user
WORKDIR /home/$the_user

CMD ["/sbin/my_init"]

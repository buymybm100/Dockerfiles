## Source : https://github.com/mascip/X11-forwarding-with-phusion-baseimage/tree/master/phusion-x11-port

# mount your local .Xauthority and .X11-unix folders to the container's filesystem
$ docker run \
    -d -P \
    -e DISPLAY \
    -v /home/ssleong/.Xauthority:/tmp/.Xauthority \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -e XAUTHORITY=/tmp/.Xauthority \
    --name=x11 buymybm100/x11

$ docker exec x11 setuser developer leafpad &


OR 

$ xhost +
$ docker exec x11 leafpad &

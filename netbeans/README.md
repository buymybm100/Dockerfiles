# Source : https://github.com/mascip/X11-forwarding-with-phusion-baseimage/tree/master/phusion-x11-port

##
## 1) At present, GRAILS 3.0 is not supported by Netbeans. 
##    Hence, after you have created a new Grails project, you can't open it
##    To use Grails 3, use the command line
##
## 2) Use Netbeans for Java/Web projects
##

$ docker build -t buymybm100/netbeans .


$ docker run \
    -d -P \
    -e DISPLAY \
    -e XAUTHORITY=/tmp/.Xauthority \
    -v /home/developer/.Xauthority:/tmp/.Xauthority \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    --name=netbeans buymybm100/netbeans

$ docker-netbeans

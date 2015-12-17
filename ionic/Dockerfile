FROM buymybm100/sdkman

# Install basics 
RUN apt-get update &&  \
    apt-get install -y git wget curl ruby && \
    apt-get clean

RUN curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -

RUN apt-get update &&  \
    apt-get install -y nodejs build-essential && \
    ln -s /usr/bin/nodejs /usr/local/bin/node && \ 
    apt-get clean

RUN gem install sass

# Install npm packages
RUN npm install -g cordova ionic
RUN npm install -g grunt-cli
RUN npm install -g gulp
RUN npm install -g bower

#RUN ionic start ionic-demo sidemenu

# Expose port: web (8100), livereload (35729)
#EXPOSE 8100 35729


#ANDROID

# ENV DEBIAN_FRONTEND noninteractive
RUN dpkg-reconfigure debconf -f Noninteractive

# install python-software-properties (so you can do add-apt-repository)
RUN apt-get update && apt-get install -y -q python-software-properties software-properties-common && apt-get clean

# Main Android SDK
RUN apt-get install -y --no-install-recommends wget
RUN cd /opt && wget -q http://dl.google.com/android/android-sdk_r22.6-linux.tgz
RUN cd /opt && tar xzf android-sdk_r22.6-linux.tgz
RUN cd /opt && rm -f android-sdk_r22.6-linux.tgz

# Git to pull external repositories of Android app projects
RUN apt-get install -y --no-install-recommends git

# Setup environment
ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

RUN echo ANDROID_HOME="${ANDROID_HOME}" >> /etc/environment



WORKDIR ionic-demo
CMD ["ionic", "serve", "8100", "35729"]

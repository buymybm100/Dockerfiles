FROM buymybm100/sdkman

ENV DEBIAN_FRONTEND=noninteractive
ENV USERNAME=developer

RUN apt-get -y -q install lxterminal \
	libxtst6 

# Install IntelliJ IDEA
RUN wget http://download.jetbrains.com/idea/ideaIC-15.0.tar.gz -O /tmp/intellij.tar.gz -q && \
    mkdir -p /opt/intellij && \
    tar -xf /tmp/intellij.tar.gz --strip-components=1 -C /opt/intellij && \
    rm /tmp/intellij.tar.gz

# Mark dev user home as data volume
VOLUME /home/$USERNAME

# Start an X terminal as dev user
WORKDIR /home/$USERNAME
ENTRYPOINT lxterminal

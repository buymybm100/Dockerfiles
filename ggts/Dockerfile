FROM buymybm100/sdkman

ENV DEBIAN_FRONTEND=noninteractive
ENV USERNAME=developer

RUN apt-get -y -q install lxterminal \
	libxtst6 

# Install IntelliJ IDEA
RUN wget http://dist.springsource.com/release/STS/3.6.4.RELEASE/dist/e4.4/groovy-grails-tool-suite-3.6.4.RELEASE-e4.4.2-linux-gtk-x86_64.tar.gz -O /tmp/ggts.tar.gz -q && \
    mkdir -p /opt/ggts && \
    tar -xf /tmp/ggts.tar.gz --strip-components=1 -C /opt/ggts && \
    rm /tmp/ggts.tar.gz

# Mark dev user home as data volume
VOLUME /home/$USERNAME

# Start an X terminal as dev user
WORKDIR /home/$USERNAME
ENTRYPOINT lxterminal

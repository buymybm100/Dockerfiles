FROM buymybm100/x11

RUN curl -sL https://deb.nodesource.com/setup_4.x | bash -
RUN apt-get install -y nodejs

ENV DEBIAN_FRONTEND=noninteractive
ENV USERNAME=developer

RUN apt-get update && \
    apt-get install -y lxterminal

ENTRYPOINT lxterminal


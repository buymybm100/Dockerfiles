FROM buymybm100/gvm

RUN wget http://download.netbeans.org/netbeans/8.1/final/bundles/netbeans-8.1-linux.sh -O /tmp/netbeans.sh -q && \
    chmod +x /tmp/netbeans.sh && \
    echo 'Installing netbeans' && \
    /tmp/netbeans.sh --silent

ADD run /usr/local/bin/netbeans

RUN chmod 777 /usr/local/bin/netbeans


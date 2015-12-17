FROM buymybm100/gvm

#Get 'petclinic' Project source code from Repository 

WORKDIR /home

#install Git
RUN apt-get update && \
    apt-get install -y git

RUN git init

RUN git pull https://github.com/buymybm100/petclinic.git

EXPOSE 8181

ENV GRAILS_OPTS -XX:-UseSplitVerifier -Xverify:none

CMD ["grails", "run-app"]

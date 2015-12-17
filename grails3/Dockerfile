## Docker - sdkman, groovy, grails, gradle
FROM buymybm100/java8

RUN apt-get update && \
    apt-get install -y wget unzip git lxterminal

ENV HOME /home/developer

RUN curl -s get.sdkman.io | bash
RUN chmod +x "$HOME/.sdkman/bin/sdkman-init.sh"
#RUN /bin/bash -c "source /$HOME/.sdkman/bin/sdkman-init.sh"

ADD sdk_wrapper.sh $HOME/sdk_wrapper.sh
RUN chmod 744  $HOME/sdk_wrapper.sh

# Install Groovy and Grails
ENV GROOVY_VERSION 2.4
ENV GRAILS_VERSION 3.0.10
ENV GRADLE_VERSION 2.9
RUN $HOME/sdk_wrapper.sh install groovy "${GROOVY_VERSION}"
RUN $HOME/sdk_wrapper.sh install gradle "${GRADLE_VERSION}"
RUN $HOME/sdk_wrapper.sh install grails "${GRAILS_VERSION}"


ENV GROOVY_HOME $HOME/.gvm/groovy/current
ENV PATH $GROOVY_HOME/bin:$PATH

ENV GRAILS_HOME $HOME/.gvm/grails/current
ENV PATH $GRAILS_HOME/bin:$PATH

ENV GRADLE_HOME $HOME/.gvm/gradle/current
ENV PATH $GRADLE_HOME/bin:$PATH

#Gradle needs TERM to work
ENV TERM dumb

ENTRYPOINT lxterminal

FROM gitpod/workspace-java-17
USER gitpod

ARG JAVA_VERSION="17.0.6-tem"

# install sdkman
RUN curl -s "https://get.sdkman.io" | bash

RUN bash -c "source $HOME/.sdkman/bin/sdkman-init.sh && \
    yes | sdk install jbang && \
    rm -rf $HOME/.sdkman/archives/* && \
    rm -rf $HOME/.sdkman/tmp/* "

# install jbang 
RUN bash -c '$HOME/.sdkman/candidates/jbang/current/bin/jbang --version'

RUN bash -c '$HOME/.sdkman/candidates/jbang/current/bin/jbang trust add https://repo1.maven.org/maven2/io/quarkus/quarkus-cli/'

# install quarkus cli
RUN bash -c '$HOME/.sdkman/candidates/jbang/current/bin/jbang app install --fresh --force quarkus@quarkusio'

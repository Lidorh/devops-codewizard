
FROM jenkinsci/blueocean:1.25.5

USER root

# Install the required docker package
RUN apk add --update docker docker-compose

ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false" \
    CASC_JENKINS_CONFIG="/usr/local/jenkins-casc.yaml"

# Copy CASC config file
COPY jenkins-casc.yaml /usr/local/jenkins-casc.yaml

# Pre-install plugins
COPY plugins.txt /usr/share/jenkins/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/plugins.txt

# Check if needed
RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

FROM jenkins/jenkins:lts-jdk17
# No utilizar en un ambiente de producción
ENV JENKINS_USER=admin
ENV JENKINS_PASS=admin
ENV JAVA_OPTS=-Djenkins.install.runSetupWizard=false
###
ADD plugins.txt .
RUN jenkins-plugin-cli -f plugins.txt
USER root
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install pylint -y
RUN apt-get install docker.io -y
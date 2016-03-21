#
# jenkins Dockerfile
#

# Pull base image.
FROM lucien/base

COPY ./jenkins.war /opt/jenkins.war

RUN chmod 644 /opt/jenkins.war
ENV JENKINS_HOME /jenkins

EXPOSE 8080
CMD ["java","-jar","/opt/jenkins.war"]

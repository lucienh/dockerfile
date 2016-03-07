#
# jira Dockerfile
#

# Pull base image.
FROM lucien/base

ENV JIRA_HOME     /var/atlassian/jira
ENV JIRA_INSTALL  /opt/atlassian/jira

COPY ./soft/* /opt/

RUN mkdir -p ${JIRA_HOME} && mkdir -p /opt/atlassian \
	&& cd opt && tar -xzvf atlassian-jira-6.3.6.tar.gz \
	&& mv /opt/atlassian-jira-6.3.6-standalone ${JIRA_INSTALL} \
	&& mv /opt/mysql-connector-java-5.1.36.jar ${JIRA_INSTALL}/atlassian-jira/WEB-INF/lib/ \
    && echo -e "\njira.home=$JIRA_HOME" >> "${JIRA_INSTALL}/atlassian-jira/WEB-INF/classes/jira-application.properties"

# Run Atlassian JIRA as a foreground process by default.
CMD ["/opt/atlassian/jira/bin/start-jira.sh", "-fg"]

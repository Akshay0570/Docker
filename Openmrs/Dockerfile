FROM maven:3.8.6-openjdk-8
RUN git clone https://github.com/openmrs/openmrs-core.git && cd openmrs-core && mvn clean package
EXPOSE 8080
WORKDIR openmrs-core/webapp
CMD ["mvn", "jetty:run"]
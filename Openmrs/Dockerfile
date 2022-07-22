FROM maven:3.8.6-openjdk-8
ADD git clone https://github.com/openmrs/openmrs-core.git 
EXPOSE 8080
WORKDIR openmrs-core/webapp
RUN cd openmrs-core && mvn clean package
CMD ["mvn", "jetty:run"]
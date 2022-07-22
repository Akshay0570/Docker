OpenMRS
Build Status Coverage Status Codacy Badge

api: API test: test tools: tools web: web webapp: webapp

OpenMRS is a patient-based medical record system focusing on giving providers a free customizable electronic medical record system (EMR).

The mission of OpenMRS is to improve health care delivery in resource-constrained environments by coordinating a global community that creates a robust, scalable, user-driven, open source medical record system platform.

Table of Contents
Build
Prerequisites
Build Command
Deploy
Docker build
Navigating the repository
Software Development Kit
Extending OpenMRS with Modules
Documentation
Developer guides
Wiki
Website
Contributing
Code
Code Reviews
Translation
Issues
Community
Support
License
Build
Prerequisites
Java
OpenMRS is a Java application which is why you need to install a Java JDK.

If you want to build the master branch you will need a Java JDK of minimum version 8.

Maven
Install the build tool Maven.

You need to ensure that Maven uses the Java JDK needed for the branch you want to build.

To do so execute

mvn -version
which will tell you what version Maven is using. Refer to the Maven docs if you need to configure Maven.

Git
Install the version control tool git and clone this repository with

git clone https://github.com/openmrs/openmrs-core.git
Build Command
After you have taken care of the Prerequisites

Execute the following

cd openmrs-core
mvn clean package
This will generate the OpenMRS application in webapp/target/openmrs.war which you will have to deploy into an application server like for example tomcat or jetty.

Deploy
For development purposes you can simply deploy the openmrs.war into the application server jetty via

cd openmrs-core/webapp
mvn jetty:run
If all goes well (check the console output) you can access the OpenMRS application at localhost:8080/openmrs.

Refer to Getting Started as a Developer - Maven for some more information on useful Maven commands and build options.

Docker build
Docker builds are still work in progress. We appreciate any feedback and improvements to the process.

The only prerequisite needed is Docker.

In order to build a development version run:

docker-compose build
It calls mvn install by default. If you would like to customize mvn build arguments you can do so by running:

docker-compose build --build-args MVN_ARGS='install -DskipTests'
It is also possible to use the built dev image to run jetty:

docker-compose up
In order to build a production version run:

docker-compose -f docker-compose.yml build
It first builds the dev image and then an image with Tomcat and openmrs.war. It has no dev dependencies.

The production version can be run with:

docker-compose -f docker-compose.yml up
Navigating the repository
The project tree is set up as follows:

api/	Java and resource files for building the java api jar file.
tools/	Meta code used during compiling and testing. Does not go into any released binary (like doclets).
web/	Java and resource files that are used in the webapp/war file.
webapp/	files used in building the war file (contains JSP files on older versions).
pom.xml	The main maven file used to build and package OpenMRS.
Software Development Kit
For rapid development of modules and the OpenMRS Platform code check out the awesome SDK at

https://wiki.openmrs.org/display/docs/OpenMRS+SDK

Extending OpenMRS with Modules
OpenMRS has a modular architecture that allows developers to extend the OpenMRS core functionality by creating modules that can easily be added or removed to meet the needs of a specific implementation.

Before creating your own module go to the OpenMRS Module Repository and see if there is already a module for your specific use case. If so deploy and try it and if a functionality is missing join the developers of the module to add a feature.

If you haven't found what you were looking for refer to the Module - wiki to learn how you can create a new module.

Documentation
Developer guides
If you want to contribute please refer to these resources

Getting Started as a Developer
How To Configure Your IDE
How To Make a Pull Request
Wiki
If you are looking for detailed guides on how to install, configure, contribute and extend OpenMRS visit

http://wiki.openmrs.org

Website
If you are looking for more information regarding OpenMRS as an organization check

http://openmrs.org

Contributing
Contributions are very welcome, we can definitely use your help!

OpenMRS organizes the privileges of its contributors in developer stages which are documented here.

Read the following sections to find out where you could help.

Code
Check out our contributing guidelines, read through the Developer guides.

After you've read up 👓 grab an introductory issue that is Ready For Work.

Code Reviews
You might not have the time to develop yourself but enough experience with OpenMRS and/or reviewing code, your help on code reviews will be much appreciated!

Read

https://wiki.openmrs.org/display/docs/Code+Review

and get started with re-👀 pull requests!

Translation
We use

https://www.transifex.com/openmrs/OpenMRS/

to manage our translations.

The messages.properties file in this repository is our single source of truth. It contains key, value pairs for the English language which is the default.

Transifex fetches updates to this file every night which can then be translated by you and me on transifex website itself. At any time we can pull new translations from transifex back into this repository. Other languages like for ex. Spanish will then be in the messages_es.properties file.

If you would like to know how to help with translations see

http://openmrs.org/join-the-community/translate/

Issues
If you want help fix existing issues or you found a bug and want to tell us please go to

https://issues.openmrs.org

Community
OpenMRS Talk OpenMRS IRC OpenMRS Telegram OpenMRS Wiki

Support
Talk to us on OpenMRS Talk

License
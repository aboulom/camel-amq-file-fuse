super-guide: Demonstrates JBoss Fuse
======================================================
Author: Allen Boulom
Level: Beginner
Technologies: Camel, Karaf
Summary: This project demonstrates how to send files between two camel routes using bundles and features.   
Target Product: JBoss Fuse 
Source: https://github.com/aboulom/super-guide

What is it?
-----------

This project demonstrates how to send files between two camel routes using bundles and features. It also demonstrates multiple bundles being run at the same time using the same configuration file. You can modify the name of the files in the configuration file and do a restart of the fuse container rather than build the project again.


System requirements
-------------------

The application this project produces is designed to be run on Red Hat JBoss Fuse 6.1 or later. 

All you need to build this project is Java 6.0 (Java SDK 1.6) or later, Maven 3.0 or later.

 
Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/CONFIGURE_MAVEN.md#configure-maven-to-build-and-deploy-the-quickstarts) before testing the project.


Use of Fuse_HOME
---------------

In the following instructions, replace `Fuse_HOME` with the actual path to your JBoss Fuse installation.


Start the JBoss Fuse Server
-------------------------

1. Open a command prompt and navigate to the root of the JBoss Fuse directory.
2. The following shows the command line to start the server:

        For Linux:   Fuse_HOME/bin/fuse.sh
        For Windows: Fuse_HOME\bin\fuse.bat


Build and install the project
-------------------------

_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/BUILD_AND_DEPLOY.md#build-and-deploy-the-quickstarts) for complete instructions and additional options._

1. Make sure you have started the JBoss Fuse server as described above.
2. Open a command prompt and navigate to the root directory of this project.
3. Type this command to build the archive:

        mvn clean install
        
4. This will install the features.xml file to the local maven repository.
5. In the fuse console, type these commands to install your project:
	
        features:addUrl mvn:com.hellofuse/features-example/1.0-SNAPSHOT/xml
        features:install features-example


Testing the project
------------------
In your Fuse_HOME directory, there should be a folder named ‘work’ that was created. 

1. Navigate to work/fuse-blueprint/input
2. Deploy your file into this directory
3. File will be transferred to work/fuse-blueprint/output
4. The file name should match with the name inside etc/rename.cfg


Uninstall the project
--------------------

1. Make sure you have started the JBoss Fuse server as described above.
2. In the fuse console, type this command to uninstall your project:

        features:uninstall {features}


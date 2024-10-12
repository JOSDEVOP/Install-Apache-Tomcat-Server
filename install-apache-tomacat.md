# Setting up TOMCAT SERVER  on CentOS
## https://downloads.apache.org/tomcat/tomcat-11/v11.0.0-M26/
## Step 1: Locate the Java Installation Path
To find the location of Java, run the following command:

```bash
#first we need to install the java jdk on the centos and we need to check the required jdk version that works well with the tomcat server
1. sudo yum  install  java-17-openjdk-devel or java-latest-openjdk-devel
2. sudo curl -o /opt/apache-tomcat-11.tar.gz https://downloads.apache.org/tomcat/tomcat-11/v11.0.0-M26/bin/apache-tomcat-11.0.0-M26.tar.gz 
3.cd /opt/ ; sudo tar -xvf /opt/apache-tomcat-11.tar.gz 
4.sudo mv apache-tomcat-11.0.0-M26   apache-tomcat-11 
# Setting the JAVA_HOME Environment Variable on CentOS

## Step 1: Locate the Java Installation Path
5.readlink -f   $(which java) 
6.sudo nano apache-tomcat-11/bin/setenv.sh - paste this here [export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-17.0.11.0.9-2.el9.x86_64] [export PATH=$PATH:$JAVA_HOME/bin] 
# Setting the JAVA_HOME Environment Variable on CentOS

7.sudo apache-tomcat-11/bin/startup.sh 



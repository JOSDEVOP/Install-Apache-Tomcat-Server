
# Apache Tomcat Setup on CentOS with Java JDK

## Prerequisites
1. **Operating System**: CentOS
2. **Required Software**: Java JDK, Apache Tomcat

## Step 1: Install Java JDK
First, we need to install the Java JDK on CentOS. Ensure you are using a version compatible with Apache Tomcat.

```bash
# Install Java JDK 17
sudo yum install java-17-openjdk-devel
# Alternatively, you can install the latest JDK version
# sudo yum install java-latest-openjdk-devel
```

## Step 2: Download Apache Tomcat
Next, download the Apache Tomcat server. In this example, we're downloading Tomcat 11.

```bash
# Download Apache Tomcat 11 to /opt directory
sudo curl -o /opt/apache-tomcat-11.tar.gz https://downloads.apache.org/tomcat/tomcat-11/v11.0.0-M26/bin/apache-tomcat-11.0.0-M26.tar.gz
```

## Step 3: Extract the Tomcat Archive
Now, extract the downloaded Tomcat archive file.

```bash
# Navigate to the /opt directory and extract the Tomcat archive
cd /opt/
sudo tar -xvf /opt/apache-tomcat-11.tar.gz
```

## Step 4: Rename the Tomcat Directory
For easier reference, rename the extracted Tomcat directory.

```bash
# Rename the extracted directory
sudo mv apache-tomcat-11.0.0-M26 apache-tomcat-11
```

## Step 5: Locate the Java Installation Path
We need to set the JAVA_HOME environment variable for Tomcat. Locate the Java installation path with the following command:

```bash
# Find the Java installation path
readlink -f $(which java)
```

## Step 6: Set the JAVA_HOME Environment Variable
Create or edit the setenv.sh file in the Tomcat bin directory to set the JAVA_HOME environment variable.

```bash
# Open or create the setenv.sh file
sudo nano apache-tomcat-11/bin/setenv.sh
```

In the file, add the following lines:

```bash
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-17.0.11.0.9-2.el9.x86_64
export PATH=$PATH:$JAVA_HOME/bin
```

> **Note**: Replace the path with the actual output from the `readlink -f $(which java)` command.

## Step 7: Start Apache Tomcat
Finally, start the Tomcat server by running the startup.sh script.

```bash
# Start the Tomcat server
sudo apache-tomcat-11/bin/startup.sh
```

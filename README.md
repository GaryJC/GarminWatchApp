## Project Name & Pitch
Team-GA-Redback

This is a software project of subject COMP90082 at The University of Melbourne. Through this project, a user with a Garmin watch can receive a workout via the CoachingMate platform. When they complete their workout, they are able to send the data from the watch to the Dashboard for viewing by themselves and their coach. In this project, our team mainly has two tasks: the frontend part and the backend part.

The backend part synchronic the data from Garmin Connect, retrieving data reflecting the status of athlete daily life, built with Springboot framework. Our main task is responsible for fixing the old version bug, as well as integrating more features into existing code. Data collected in Garmin Connect is acquired through Garmin wearable. Data will be displayed on the frontend part.

The frontend part is mainly about the development of the dashboard. We need to design better user interfaces based on human-computer interaction theory. Visualize the data collected by the backend and present them to the user.

## Project Status

This project is currently in development.
1. user is able to create an account, synchronizing the data retrieve from Garmin connect.
2. user’s data saved in the MongoDB database in a standard way, which is convenient for future development.
3. user can view all his activity data, under viewing of the list.
4. completely fix the bug of the old version

Future tasks:：
1. create more api retrieving data for front end, including activity details, and echo data.
2. delete redundant code

## Backend Flow

The backend built with Springboot framework, it including following function
Garmin Part
1) synchronic data from garmin connect
2) store in mongodb database

Web part
1) Connect user with garmin connect
2) Store user info in mongodb database
3) Giving user visulization on his exercise history

![image](https://user-images.githubusercontent.com/82303079/163653500-0cb0d473-de5f-4e4e-9987-455504e8e867.png)

## Installation and Setup Instructions

### 1. install JDK
[Official tutorial for JDK installation](https://docs.oracle.com/javase/10/install/installation-jdk-and-jre-macos.htm#JSJIG-GUID-2FE451B0-9572-4E38-A1A5-568B77B146DE)

### 2. install maven
[Official tutorial for Maven installation](http://maven.apache.org/install.html)<br>
take mac os for example
- download 	apache-maven-3.6.3-bin.tar.gz
- tar xzvf apache-maven-3.6.3-bin.tar.gz
 * Alternatively use your preferred archive extraction tool.
 * Add the bin directory of the created directory apache-maven-3.6.3 to the PATH environment variable
 * Confirm with mvn -v in a new shell. The result should look similar to
```
Apache Maven 3.6.3 (cecedd343002696d0abb50b32b541b8a6ba2883f)
Maven home: /opt/apache-maven-3.6.3
Java version: 1.8.0_45, vendor: Oracle Corporation
Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "mac os x", version: "10.8.5", arch: "x86_64", family: "mac"
```
### 3. install MongoDB
[Official tutorial for mongoDB installation](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)

```
brew install mongodb-community@4.4
```

### 4. install git environment
- linux install
```
yum install git
```
- mac install
```
brew install git
```
- Before you can use Git for version management, you need to configure Git by telling git your **username** and your **email account**
```
//configuration
[root@localhost ~]# git config --global user.name flymegoc
[root@localhost ~]# git config --global user.email 343672271@qq.com

//Check the configuration
[root@localhost ~]# git config --list
user.name=flymegoc
user.email=343672271@qq.com
```

### 5. Run this project locally
Clone down this repository. You will need `maven` and `JDK1.8` installed globally on your machine.  

`git clone https://github.com/agogear/coaching-mate.git`

Modify configuration file:
[application-dev.properties](https://github.com/agogear/coaching-mate/blob/master/src/main/resources/application-dev.properties)

1. create your mongodb database with {database name} manually on your local environment
```
spring.data.mongodb.database={database name}
spring.data.mongodb.port=27017
```
2. export data from cloud database:
[cloud mongodb database](mongodb+srv://admin:unimelb0121@cluster0.2qpx8.mongodb.net/coachingMate?retryWrites=true&w=majority)
3. import data to your local mongodb database


Installation:

`cd coachingmate` <br>
`mvn install`  

To Start Server:

`java -jar ./target/coachingmate-0.0.1-SNAPSHOT.jar`  

To login App:

`localhost:8080/login?username={username}&password={password}`  


## Deployment guidelines
There are serveal steps we need to do to run our app on heroku
### 1. create a new application on heroku
![image](https://github.com/chenyuguo/coachingmate/blob/master/Resources/runonserver/picture/pic/1newApp.jpg)

### 2. text our app name and region
![image](https://github.com/chenyuguo/coachingmate/blob/master/Resources/runonserver/picture/pic/2newCreate.jpg)

### 3. fork this repository to your own repository

### 4. Select Github and find this forked project in your own repository
![image](https://github.com/chenyuguo/coachingmate/blob/master/Resources/runonserver/picture/pic/3connect.jpg)

### 5. connect successfully
![image](https://github.com/chenyuguo/coachingmate/blob/master/Resources/runonserver/picture/pic/4success.jpg)

### 6. find our app and click the Openapp button
![image](https://github.com/chenyuguo/coachingmate/blob/master/Resources/runonserver/picture/pic/5open.jpg)

### 7. find our URL in the build log
![image](https://github.com/chenyuguo/coachingmate/blob/master/Resources/runonserver/picture/pic/6.jpg)

URL: <https://coachingmate2020.herokuapp.com/>

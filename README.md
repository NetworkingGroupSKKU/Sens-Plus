Sens-Plus
=========
USAGE CONTEXT SHARING

###THE RELATED TECHNOLOGY###
There have been many android monitoring applications up to now. The academic researchers and industrial developers develop applications to measure device usage and context information. Such applications are usually used to analyze the user patterns in order to provide the better services to mobile phone users. Most of the applications have been developed for the purpose of collecting directly interesting information such as device’s information, user mobility. However, there is no common application which can provide sufficient feedback from users, such as SMS (number of sending and receiving messages), Call (number of call and receive), Battery used, Applications used in daily life. Our objective is to develop an application for above requirements.
 
###INTRODUCTION OF THE APPLICATION###
We investigate “How is the device being used by the users, e.g. calls, SMS, applications activity, etc. in a daily life? This software is designed to install in the Android smart phone to collect the usage context from the user. After install this application, the logging function is run to capture the common information from the usage behaviors of the users such as the amount of call, SMS, battery, and application used in a day. The logged data are stored in the memory of mobile phone and then are sent to the management server. The major consideration of this application is to keep low profile, energy consumption. Therefore, the application is designed to be invisible. In other words, it has no user interface to minimize impact of usage, and therefore it has small footprint in term of memory.
 
###EXISTING TECHNOLOGIES ISSUES###
The existing Android SDK provides the tools with many supported API. It provides a good environment to developer to develop their own idea based on some specific situations and scenarios. Java programming is one of a famous programming language in computer sciences. With good understanding about Java language, developers can implement their idea on Android SDK using Java language. It is note that the Java programming in Android environment is different with the aboriginal one, but they have a lot similar in structure-wise.
 
###THE GOAL OF THE APPLICATION###
In the research of interaction science, analyzing the today mobile phone users’ patterns is one of important issues for providing better QoS. Thus this software is an efficient solution for collect data from users automatically without any effect to user behaviors. Moreover, the application was developed in an extendable way so that we can easy to modify and upgrade for further requirements.
 
###THE EFFECT OF THE APPLICATION###
Using this application, researchers and developers can save a lot of time and effort to collecting the smart phone patterns. Though it collect the information from the mobile phone users, only the common usage context are collected. Thus it does not violate any privacy issue due to the limited of collected information. For example, we collect only the number of sending and receiving call, SMS but it does not capture the conversation information.
The application can work properly with all android phone starting from API-8 ( Android 2.2)
 
###THE EXPLANATION OF THE APPLICATION###
To collect information from mobile phone users, we have to get the event from the integrated sensors inside the Android phone. The usage information that can be collected:
* **Calling information**: IMEI, call time, callee’s phone number, call type (ringing, call, end), and duration time.
* **SMS message information**: IMEI, sender’s phone number, message length, receiving and sending time.
* **Battery information**: IMEI, level(%), temperature(C degree), health (Good, Bad, Average), and voltage.
* **Recent used application**: IMEI, App number and application's name
(example: com.android.phuc.nfc.NFC, com.rovio.ka3d.App, or com.android.phuc.systemsens.Sens_Plus etc.).

First, application runs in the background service, and it periodically captures the battery and used information from the users. We set the period of 5 minutes to capture battery and used information. Note that this period of time can be easy to adjust. Second, the event-tracking function is used to detect call, SMS information from users. Whenever the user using call, SMS function, the information about phone number, call type, call time, SMS sending number, and message length are recorded. Last, the captured data in memory will be sent to server using an uploading mechanism.
 
###THE EXPERIMENT INFORMATION###
The application has been passed through an extensive experiment. It is running smoothly on Samsung Galaxy SII and Galaxy Nexus devices without any problem. Moreover, it has not much effect too much to the energy consumption and users complain. Currently, with a database server, it shows a good execution result. We can easy to see all the recorded information uploaded by our application by access to server.
 
###DATABASE & WEB SERVER DEVELOPMENT###
Our server configuration consists of a MySQL database on a Window 7 machine running Apache. When the server receives a post request from a client it parses the JSON object and inserts the type, user, and date records along with the original JSON string in a database table.

**Web Server specifications**
* Intel(R) Core(TM)2 Duo E8400 @ 3.00 GHz
* 4G Memory

**Server installed programs**
* Web Server: Apache 1.3.41-1
* Name Server: bind-9.3.4-1
* Database Server: mysql-5.0.51-1, mysql-client-5.0.51-1
* Script language: php-5.2.6-7, php-extension-5.2.6-7, php-gd-5.2.6-7, php-json-5.2.6-7, php-mcrypt-5.2.6-7, php-mysql-5.2.6-7, php-mysqli-5.2.6-7, php-openssl-5.2.6-7

**Database management tools**
* phpmyadmin: 3.3.9.2
* Url: http://log.nzin.net/phpmyadmin/

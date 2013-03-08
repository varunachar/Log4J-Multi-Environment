Log4J-Multi-Environment
=======================

Basic files needed for configuring log4j to run in multiple environments

<p>
Log4JInitializer is a servlet which will programtically initialize log4. This method is the most flexible way of configuring log4j 
according to it's author. Besides a servlet, it can also be initialized in a ServletContextListener or any other Java Program which
runs before anything else in your application.
</p>

<p>
The web.xml file contains the entry needed for configuring the server to execute Log4JInitializer. 
</p>

<p> 
Log4JInitializer reads an environment variable and uses that to load the environment specific configuration. So name your log4j config files
like log4j-dev.properties, log4j-prod.properties, log4j-test.properties, log4j-stage.properties 
</p>

<p>
For Windows set the Environment variable as you would normally do.
<br>
For Linux, edit the {CATALINE_HOME}/conf/tomcat7.conf file or the catalina.sh file and add 
<br> 
<code>
export MY_ENVIRONEMENT_VARIABLE=prod
</code>
</p>
<br>
<p>
And viola, you now have a environment specific log4j!<br>
Cheers!
</p>

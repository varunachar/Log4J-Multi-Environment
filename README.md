Log4J-Multi-Environment
=======================

Basic files needed for configuring log4j to run in multiple environments

How does it work
=================
Log4J has a nifty class called PropertyConfigurator which does the work. Simply read the property file from the classpath and pass it
to PropertyConfigurator's configure method and you're done!<br><br>
<p>
<b>BONUS<b>: PropertyConfigurator has another method called configureAndWatch which creates a separate thread for watching the property
file for changes. If you change the configuration of the log4j while the application is running, PropertyConfigurator will reconfigure 
log4j on the fly! No server restarts required! Happy debugging!
</p>
<p>
Log4jInitializer is a servlet which will programtically initialize log4. This method is the most flexible way of configuring log4j 
according to it's author. Besides a servlet, it can also be initialized in a ServletContextListener or any other Java Program which
runs before anything else in your application.
</p>

<p>
The web.xml file contains the entry needed for configuring the server to execute Log4JInitializer. 
</p>

<p> 
Log4jInitializer reads an environment variable and uses that to load the environment specific configuration. So name your log4j config files
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
And viola, you now have an environment specific log4j!<br>
Cheers!
</p>

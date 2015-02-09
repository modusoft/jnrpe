#Welcome to the JNRPE package

The JNRPE addon is a Java replacement of NRPE and is designed to allow you to execute Nagios plugins on remote machines. 
Differently from NRPE, JNRPE gives you the ability to execute plugins written using the Java language without the
 overhead of many short lived JVM instances (NRPE executes the plugins as external executables: that means that to execute a Java plugin, one JVM must be started for each java-written plugin execution).
  
The main reason for using JNRPE is to allow Nagios to monitor "local" resources on remote machines with 'write once, run everywhere' plugins. Moreover, JNRPE itself is a Java application, so it can run on all the operating systems where Java runs removing the limit to Unix/Linux.

##How JNRPE works

![images/deployment.png](JNRPE deployment.)

The Nagios plugins will be executing as follows:
  
  1. Nagios will invoke a check defined as a check_nrpe command.
  2. check_nrpe will invoke the command on the JNRPE server
  3. The JNRPE server will invoke the plugin associated with the requested command
  4. The plugin will perform the check. If the plugin is the NATIVE check plugin, 
  the external executable will be invoked and its output will be returned. This plugin is
  useful if you want to use a mix of java and executable plugins since you don't have to
  install both JNRPE and NRPE.
  5. JNRPE receives the plugin output and returns it to check_nrpe
  6. check_nrpe returns the check result to Nagios
  
##How to Get Support

  TBD
 
##How can I Help?

 JNRPE is an open source community and welcomes contributions. 
 If you'd like to get involved, please send me an e-mail.
 
##Donations

If you would like to support the continued development of JNRPE, you can make a donation like 5-10 Euros/US$ or whatever you feel that JNRPE is worth to you. 
Please note that this is not payment for JNRPE, but an optional donation to the project -- JNRPE is always free to use.
 
Click [here](http://sourceforge.net/donate/index.php?group_id=204486) to make a donation.

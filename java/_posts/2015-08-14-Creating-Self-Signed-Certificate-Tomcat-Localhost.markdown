---
layout:     post
title: 	    Creating a Self-Signed Certificate for SSL on Tomcat Localhost 
date:       2015-08-14 12:00:00
summary:    Quick reference guide for setting SSL on your local Tomcat instance
categories: Tomcat 
---
A quick reference guide for setting SSL on your local Windows Tomcat instance. You can see the [Tomcat Docs](http://tomcat.apache.org/tomcat-7.0-doc/ssl-howto.html) for the official instructions.

1. Create the keystore file:  

    "%JAVA_HOME%\bin\keytool" -genkey -alias tomcat -keyalg RSA -keystore keystore.jks

Note: you probably do want to explicitly name the keystore file. `.jks` is a [repository of security certificates](https://en.wikipedia.org/wiki/Keystore). The `-genkey` command creates a `.keystore` filetype by default which is a more generic type.  

2. Add the SSL configuration to the Tomcat server. Two parts- uncomment the SSL connector in the Tomcat server config and add the keystore (which has only one key for a fresh keystore gen).    
    
    path\to\Apache Software\Tomcat7.0\conf\server.xml  

    <!--Connector port="8443" protocol="org.apache.coyote.http11.Http11Protocol" maxThreads="150" SSLEnabled="true" scheme="https" secure="true" keystoreFile="path/to/ye/olde/keystore.jks" keystorePass="ye-olde-password" clientAuth="false" sslProtocol="TLS" /-->

3. Double-check for AJP. For this config, I am not using AJP, so I needed to change the protocol from AJP to HTTP [source](http://stackoverflow.com/a/28774605):  

   <!-- Define an AJP 1.3 Connector on port 8009 --> 
   <!--Connector URIEncoding="UTF-8" port="8029" protocol="HTTP/1.1" redirectPort="8443"/-->

Another great resource:   

[Common Keytool Commands](http://shib.kuleuven.be/docs/ssl_commands.shtml)

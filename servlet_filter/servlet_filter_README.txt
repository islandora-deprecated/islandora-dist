This is a quick set of instructions for getting Fedora up and running
so taht it can connect to a Drupal database for authentication. A more
detailed explanation of how the servlet filter works can be found in the
islandora guide at DuraSpace:

https://wiki.duraspace.org/display/ISLANDORA/Islandora+Guide#IslandoraGuide-DrupalServletFilter

This file assuems you have Fedora's required environment variables
set up, e.g., $FEDORA_HOME and $CATALINA_HOME (The location of the Tomcat
where Fedora is deployed.)


With FeSL Authentication Enabled
================================

Copy fcrepo-drupalauthmodule-3.4.2 to $CATALINA_HOME/webapps/fedora/WEB-INF/lib
Either copy jaas.conf to $FEDORA_HOME/server/config or modify your copy to 
include the line that lists the DrupalAuthModule class.

Configure filter-drupal.xml as described below. You do not need to modify
web.xml in this case.


With FeSL Authentication Disabled
=================================

Copy the appropriate .jar file for your version of Fedora to 
$CATALINA_HOME/webapps/fedora/WEB-INF/lib.


web.xml
-------

Add entries for the Drupal servlet filter into the filter and 
filter-mappings sections of Fedora's web.xml file located at
$CATALINA_HOME/webapps/fedora/WEB-INF/web.xml.

See example below:
    
    <filter>
         <filter-name>XmlUserfileFilter</filter-name>
         <filter-class>fedora.server.security.servletfilters.xmluserfile.FilterXmlUserfile</filter-class>
    </filter>
    <filter>
         <filter-name>DrupalFilter</filter-name>
         <filter-class>ca.upei.roblib.fedora.servletfilter.FilterDrupal</filter-class>
    </filter>
    <filter>
          <filter-name>RestApiAuthnFilter</filter-name>
          <filter-class>org.fcrepo.server.security.servletfilters.FilterRestApiAuthn</filter-class>
    </filter>
    
And here

    <filter-mapping>
         <filter-name>XmlUserfileFilter</filter-name>
         <url-pattern>/*</url-pattern>
    </filter-mapping>
    <filter-mapping>
          <filter-name>DrupalFilter</filter-name>
          <url-pattern>/*</url-pattern>
    </filter-mapping>
    <filter-mapping>
          <filter-name>EnforceAuthnFilter</filter-name>
          <servlet-name>AxisServlet</servlet-name>
    </filter-mapping>


filter-drupal.xml
=================

Copy filter-drupal.xml to $FEDORA_HOME/server/config

Edit the file to match the database settings in your Drupal site's
settings.php file.

Restart Fedora. The Drupal filter should now be in place.

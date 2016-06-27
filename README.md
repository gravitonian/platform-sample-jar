# Alfresco Platform JAR Module - SDK 3

This is a sample module for the [Alfresco SDK 3.x PoC](https://github.com/Alfresco/alfresco-sdk/tree/sdk-3.0). To run this module, please clone the Alfresco SDK and install the `sdk-3.0` branch. Install with `mvn clean install -DskipTests=true`

Then clone this module and run with `mvn clean install -DskipTests=true alfresco:run` or `./run.sh` and verify that it 

 * Runs the embedded Tomcat+H2 DB (and Solr4)
 * Packages both as JAR and AMP assembly
 
 Try cloning it twice, change the port and play with `enableShare`, `enableRepository` and `enableSolr`. Protip: This module will work just fine as a Share module if the files are changed if the repository and solr is disabled.
 
# Few things to notice

 * No parent pom
 * Standard JAR packaging and layout
 * Works seamlessly with Eclipse and IntelliJ IDEA
 * JRebel for hot reloading, JRebel maven plugin for generating rebel.xml, agent usage: `MAVEN_OPTS=-Xms256m -Xmx1G -agentpath:/home/martin/apps/jrebel/lib/libjrebel64.so`
 * AMP as an assembly
 * [Configurable Run mojo](https://github.com/Alfresco/alfresco-sdk/blob/sdk-3.0/plugins/alfresco-maven-plugin/src/main/java/org/alfresco/maven/plugin/RunMojo.java) in the `alfresco-maven-plugin`
 * No unit testing/functional tests just yet
 * Resources loaded from META-INF
 * Web Fragment (this includes a sample servlet configured via web fragment)
 
# TODO
 
  * Create example module for Share
  * Abstract assembly into a dependency so we don't have to ship the assembly in the archetype
  * Create new, slim and simply parent pom to set sensible defaults and profiles
    * Purge, functional/remote unit tests
    * Ensure that all functionality still works even without parent pom
   
  
 

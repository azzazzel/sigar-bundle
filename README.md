Sigar-Bundle
============

An OSGi wrapper bundle for Hyperic Sigar. https://github.com/hyperic/sigar

Author: Simon Chemouil
(c) 2014, Lambdacube


============

Just use build it using `mvn install` or deploy on your Nexus. It's not deployed on Maven Central but if you think it should drop me a mail.

You must use set the framework property `org.osgi.framework.bootdelegation` to `sun.misc`. Be careful, the bundle will install  in your OSGi container without complaining, since I prevent bnd from adding the Import-Package clause on `sun.misc` because then Bnd can't resolve it with the JavaSE-1.x profile. This is not a problem for me since I use Sigar with Akka Cluster, which already requires delegating the sun.misc package to the boot classloader.

Also, Sigar depends on log4j 1.2.x. I suggest using the log4j 1.2.17 (as of today) available on Maven Central. It is a valid OSGi bundle. 

    <dependency>
        <groupId>log4j</groupId>
       <artifactId>log4j</artifactId> 
      <version>1.2.17</version>
    </dependency>


Enjoy.

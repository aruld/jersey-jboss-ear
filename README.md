jersey-jboss-ear: Jersey JAX-RS Example Deployed as an EAR in JBoss 7
=====================================================================

Based on the template from https://github.com/jboss-jdf/jboss-as-quickstart/tree/jdf-2.0.0.Final/kitchensink-ear

System requirements
-------------------

All you need to build this project is Java 6.0 (Java SDK 1.6) or better, Maven 3.0 or better.

The application this project produces is designed to be run on JBoss Enterprise Application Platform 6 or JBoss AS 7.


Start JBoss Enterprise Application Platform 6 or JBoss AS 7 with the Web Profile
-------------------------

1. Open a command line and navigate to the root of the JBoss server directory.
2. The following shows the command line to start the server with the web profile:

        For Linux:   JBOSS_HOME/bin/standalone.sh
        For Windows: JBOSS_HOME\bin\standalone.bat


Build and Deploy the EAR
-------------------------

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this project.
3. Type this command to build and deploy the archive:

        mvn clean package jboss-as:deploy

4. This will deploy `target/jersey-jboss-ear.ear` to the running instance of the server.


Access the application
---------------------

The application will be running at the following URL: <http://localhost:8080/jersey-jboss-ear-web/helloworld>.

It just prints:

        Hello World


Undeploy the Archive
--------------------

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this project.
3. When you are finished testing, type this command to undeploy the archive:

        mvn jboss-as:undeploy


Investigate the Server Console Output
---------------------
You should see messages similar to the following:

    21:49:20,354 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-10) JBAS015876: Starting deployment of "jersey-jboss-ear.ear"
    21:49:20,407 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-3) JBAS015876: Starting deployment of "jersey-jboss-ear-web-1.0-SNAPSHOT.war"
    21:49:20,581 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootElementProvider$App' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,582 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootElementProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,583 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootElementProvider$General' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,584 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLJAXBElementProvider$App' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,584 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLJAXBElementProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,585 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLJAXBElementProvider$General' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,586 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLListElementProvider$App' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,587 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLListElementProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,588 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLListElementProvider$General' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,589 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.SourceProvider$StreamSourceReader' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,590 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.SourceProvider$SAXSourceReader' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,590 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.SourceProvider$DOMSourceReader' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,591 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootObjectProvider$App' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,592 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootObjectProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,593 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootObjectProvider$General' for service type 'javax.ws.rs.ext.MessageBodyReader'
    21:49:20,594 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootElementProvider$App' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,595 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootElementProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,596 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLRootElementProvider$General' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,597 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLJAXBElementProvider$App' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,598 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLJAXBElementProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,599 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLJAXBElementProvider$General' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,600 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLListElementProvider$App' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,601 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLListElementProvider$Text' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,601 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.XMLListElementProvider$General' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,602 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.core.impl.provider.entity.SourceProvider$SourceWriter' for service type 'javax.ws.rs.ext.MessageBodyWriter'
    21:49:20,604 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.server.impl.model.parameter.multivalued.StringReaderProviders$TypeFromStringEnum' for service type 'com.sun.jersey.spi.StringReaderProvider'
    21:49:20,605 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.server.impl.model.parameter.multivalued.StringReaderProviders$TypeValueOf' for service type 'com.sun.jersey.spi.StringReaderProvider'
    21:49:20,606 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.server.impl.model.parameter.multivalued.StringReaderProviders$TypeFromString' for service type 'com.sun.jersey.spi.StringReaderProvider'
    21:49:20,606 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.server.impl.model.parameter.multivalued.StringReaderProviders$StringConstructor' for service type 'com.sun.jersey.spi.StringReaderProvider'
    21:49:20,607 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.server.impl.model.parameter.multivalued.StringReaderProviders$DateProvider' for service type 'com.sun.jersey.spi.StringReaderProvider'
    21:49:20,608 WARN  [org.jboss.as.server.deployment] (MSC service thread 1-5) JBAS015893: Encountered invalid class name 'com.sun.jersey.server.impl.model.parameter.multivalued.JAXBStringReaderProviders$RootElementProvider' for service type 'com.sun.jersey.spi.StringReaderProvider'
    21:49:20,733 WARN  [org.jboss.jaxrs] (MSC service thread 1-7) JBAS011204: resteasy.scan found and ignored in web.xml. This is not necessary, as Resteasy will use the container integration in the JAX-RS 1.1 specification in section 2.3.2
    21:49:20,734 WARN  [org.jboss.jaxrs] (MSC service thread 1-7) JBAS011204: resteasy.scan.providers found and ignored in web.xml. This is not necessary, as Resteasy will use the container integration in the JAX-RS 1.1 specification in section 2.3.2
    21:49:20,735 WARN  [org.jboss.jaxrs] (MSC service thread 1-7) JBAS011204: resteasy.scan.resources found and ignored in web.xml. This is not necessary, as Resteasy will use the container integration in the JAX-RS 1.1 specification in section 2.3.2
    21:49:20,877 INFO  [com.sun.jersey.server.impl.application.WebApplicationImpl] (MSC service thread 1-2) Initiating Jersey application, version 'Jersey: 1.16 11/28/2012 02:09 PM'
    21:49:20,913 INFO  [com.sun.jersey.server.impl.application.DeferredResourceConfig] (MSC service thread 1-2) Instantiated the Application class com.sun.jersey.samples.helloworld.resources.MyApplication
    21:49:21,305 INFO  [org.jboss.web] (MSC service thread 1-2) JBAS018210: Registering web context: /jersey-jboss-ear-web
    21:49:21,334 INFO  [org.jboss.as.server] (management-handler-thread - 1) JBAS018559: Deployed "jersey-jboss-ear.ear"


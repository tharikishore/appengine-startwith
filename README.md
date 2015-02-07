## Google Appengine + Gaelyk + Cloud SQL/App Engine native Hibernate JPA demo

* This project is build with gradle 
* Is configured to use Hibernate (if needed)
* Configured for Gaelyk


## Requirements

* [Apache Maven](http://maven.apache.org) 3.0 or greater
* Gradle
* a local MySQL server (for running locally with devserver)
* JDK 7+

Clone this repository to a local directory.  Maven will download all the other dependencies.


## Deploying - Maven

To build, run:

    mvn package

## Deploying - Gradle

	gradle build

## Local deployment

Make sure the `demo` database exists on the local MySQL server.

To start the app, use the [App Engine Maven Plugin](http://code.google.com/p/appengine-maven-plugin/) that is included in this demo.  Just run the command:

    mvn appengine:devserver
    	or
    gradle appengineRun


## App Engine deployment - Maven

In `pom.xml` update the following properties:

* `appengine.app.appId` to point to your App Engine application ID
* `cloudsql.url` to point to your Cloud SQL instance by replacing `your-instance-name` with the full name of your instance (this looks either like `my_project:my_instance` for non-domain specific instances or like `my_domain:my_project:my_instance` for the domain-specific ones).

Make sure the `demo` database exists on the Cloud SQL instance.

To deploy the app run the following command:

    mvn appengine:update
    	or
    gradle appengineUpdate


## Contributing changes

* See [CONTRIB.md](CONTRIB.md)


## Licensing

* See [LICENSE](LICENSE)

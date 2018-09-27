# DBConnectionPooling

What is Connection Pooling? 
In many of our applications we need to connect to the database for various purposes such as inset, update , delete and retrieve the data from the DB. For each of these activities the application needs to connect to the database which is expensive in terms of resource as well as time. Instead of connecting to the database each time a user makes a request which requires database operation an application should use a pool of connections. Then each application thread that needs to access the database can request a connection from the pool and returns the same to the pool when all the database operations have been executed. This mechanism is called connection pooling.
Why do we use connection pooling?

Connection Pooling has a number of advantages.

1. Connection Pooling improves performance.
2. It is very much expensive for a database management system to maintain many idle connections. But with connection pooling the use of idle connection can be minimized by disconnecting the connection to db if there are no requests.
3. We can manage the connection parameters at one place lets say in a config or properties file.
Different Types of Connection Pooling mechanism

Hibernate supports various types of connection pooling mechanisms such as 
C3P0 (Custom 3rd-Party Object) - https://sourceforge.net/projects/c3p0/, 
Apache DBCP - http://commons.apache.org/dbcp/, 
Proxool. C3P0 is an Open source connection pool that comes bundled with hibernate.
How to configure c3p0 connection pool in Hibernate

To use c3p0 connection pooling we need to copy c3p0-0.9.1.1.jar file into the classpath.

I've used following Application servers and connection pooling mechanism are listed below
  1. Apache Tomcat - It has c3p0 in the Lib folder.
  2. TCServer - No Connection pooling machanism inbuilt. So we have to use c3p0 or Apache DBCP in the code to use those.
  3. JBOSS EAP
  
  If you're running in a web application container, use the built-in connection pooling of your container.

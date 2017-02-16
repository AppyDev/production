
##REPORT


### Issues faced in iTrust

1. Issues getting the Java JDK because there were a few version compatibility problems. We solved this by removing the older versions, identified the java version in use and switched to the appropriate version.
2. Issues getting apache tomcat unarchived since many installation files were outdated.
3. Memory assigned to the VM had to be changed manually. We solved this by editing the Vagrant file to accomodate the extra memory.
4. Cloning private Git repository [iTrust] with the necessary credentials. This was solved by using environment variables.
5. Starting tomcat from ansible.


### Steps to build iTrust

1. Clone iTrust repository
2. Install dependencies such as Maven, Java 8, JDK 1.8, MySQL, Tomcat, JDBC Connector.
3. Ensure all tables have lower case names by editing /etc/mysql/my.cnf by adding "lower_case_table_names=1" under [mysqld] section.
4. Start Tomcat by running startup.sh script.
5. Start MySQL service.
6. Initiate the iTrust build using the "mvn clean package" command in iTrust.
7. Copy the war file generated in iTrust/target into the webapps folder of Apache tomcat.
8. Restart tomcat.
9. Go to the IP:8080/iTrust_war_filename to view the login page. 




##SCREENCAST

1. iTrust - https://www.youtube.com/watch?v=hux_0EK0Taw&feature=youtu.be&hd=1

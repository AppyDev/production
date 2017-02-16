
##REPORT


### Issues faced in iTrust

1. Issues getting the Java JDK because there were a few version compatibility problems. We solved this by removing the older versions, identified the java version in use and switched to the appropriate version.
2. Issues getting apache tomcat unarchived since many installation files were outdated.
3. Memory assigned to the VM had to be changed manually. We solved this by editing the Vagrant file to accomodate the extra memory.
4. Cloning private Git repository [iTrust] with the necessary credentials. This was solved by using environment variables.
5. Starting tomcat from ansible.


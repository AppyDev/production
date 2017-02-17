
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

### Issues faced in checkbox.io

1. Mongodb connection string
2. Dependencies to run checkbox.io
  The existing package.json was missing some dependencies to setup the project. As we progressed with npm install, we encountered missing packages and updated the package.json
3. SMTP email server settings
4. Running the nodejs application from ansible
5. Cloning private repository from with necessary credentials. 

### Steps to run checkbox.io

1. Add following environment variables in your bash:
  
  ```
    export SMTPEMAIL = <Your-email-id>
    export SMTPEMAIL = <Your-password>
    export GITUSER = <Your-ncsu-github-email-id>
    export GITPWD = <Your-ncsu-github-password>
    export MONGOUSER = <mongo_user_name>
    export MONGOPWD = <mongo_user_password>
  ```
2. Load bashrc into new shell
  
  ```
    source ~/.bashrc
  ```
3. Clone the repository

  ```
    git clone https://github.ncsu.edu/akpatil/CSC519-Project.git
  ```
4. Change directory
  
  ```
    cd CSC519-Project/M1/nodejsProject/checkbox.io
  ```
5. Run ansible script
  
  ```
    ansible-playbook -i inventory checkboxio.yml
  ```
  
##WORK SPLIT

iTrust - Keshav Parthasarathy (kpartha2) and Sharath Sreenivasan (ssreeni)

checkboxio - Aparna Patil (akpatil) and Shreya Pagedar (svpageda)

##SCREENCAST

1. iTrust - https://www.youtube.com/watch?v=hux_0EK0Taw&feature=youtu.be&hd=1
2. checkboxio - 

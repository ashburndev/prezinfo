On March 15 I used Grails 5.2.4 to create a new Grovvy on Grails web application named prezinfo.

Here is the MySQL database (and account) I created to support the prezinfo Grails web application.

    DROP DATABASE IF EXISTS prezdb;
    DROP USER 'prez'@'localhost';
    CREATE USER 'prez'@'localhost' IDENTIFIED BY 'prezpw';
    DROP  prezdb;
    CREATE DATABASE prezdb;
    GRANT ALL PRIVILEGES ON prezdb.* TO 'prez'@'localhost' WITH GRANT OPTION;

    mysql> show databases;
    +--------------------+
    | Database           |
    +--------------------+
    | db_example         |
    | depot2_development |
    | dphpyapp1          |
    | dphpyapp2          |
    | information_schema |
    | mysql              |
    | performance_schema |
    | prezdb             |
    | sbapp2db           |
    | sbapp3db           |
    | sys                |
    | tacocloud          |
    | wire2_development  |
    | wire3_development  |
    | wire4_development  |
    | wire5_development  |
    | wire6_development  |
    +--------------------+
    17 rows in set (0.04 sec)

    mysql> 

Here are the software versions I am currently using on my Dell XPS 17 (Ubuntu 22.04):

    davidho@dphxps17:~$ sdk current

    Using:

    ant: 1.10.12
    asciidoctorj: 2.5.4
    gradle: 8.0.2
    grails: 5.3.2
    groovy: 4.0.9
    java: 17.0.6-zulu
    maven: 3.9.0
    davidho@dphxps17:~$ 
    davidho@dphxps17:~$ printenv | grep -i _HOME
    ASCIIDOCTORJ_HOME=/home/davidho/.sdkman/candidates/asciidoctorj/current
    JAVA_HOME=/home/davidho/.sdkman/candidates/java/current
    GRADLE_HOME=/home/davidho/.sdkman/candidates/gradle/current
    ANT_HOME=/home/davidho/.sdkman/candidates/ant/current
    GROOVY_HOME=/home/davidho/.sdkman/candidates/groovy/current
    MAVEN_HOME=/home/davidho/.sdkman/candidates/maven/current
    GRAILS_HOME=/home/davidho/.sdkman/candidates/grails/current
    davidho@dphxps17:~$ 
    davidho@dphxps17:~$ java --version
    openjdk 17.0.6 2023-01-17 LTS
    OpenJDK Runtime Environment Zulu17.40+19-CA (build 17.0.6+10-LTS)
    OpenJDK 64-Bit Server VM Zulu17.40+19-CA (build 17.0.6+10-LTS, mixed mode, sharing)
    davidho@dphxps17:~$ 
    davidho@dphxps17:~$ gradle --version

    ------------------------------------------------------------
    Gradle 8.0.2
    ------------------------------------------------------------

    Build time:   2023-03-03 16:41:37 UTC
    Revision:     7d6581558e226a580d91d399f7dfb9e3095c2b1d

    Kotlin:       1.8.10
    Groovy:       3.0.13
    Ant:          Apache Ant(TM) version 1.10.11 compiled on July 10 2021
    JVM:          17.0.6 (Azul Systems, Inc. 17.0.6+10-LTS)
    OS:           Linux 5.19.0-35-generic amd64

    davidho@dphxps17:~$ 


more documentation ...

    mkdir ~/grailsprojs
    cd ~/grailsprojs

    grails create-app prezinfo
    cd prezinfo
    grails run-app
    grails run-app -port=8090
    grails run-app -Dgrails.server.servlet.context-path=/prezinfo
    grails test-app

    grails war
    java -Dgrails.env=prod -jar build/libs/mywar-0.1.war

    grails create-domain-class president

    - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - 

    davidho@dphxps17:~/grailsprojs/prezinfo$ ls -latr
    total 72
    -rwxrw-r--  1 davidho davidho 2763 Mar 15 07:05 gradlew.bat
    -rwxrw-r--  1 davidho davidho 5766 Mar 15 07:05 gradlew
    drwxrwxr-x  3 davidho davidho 4096 Mar 15 07:05 gradle
    drwxrwxr-x  3 davidho davidho 4096 Mar 15 07:05 ..
    drwxrwxr-x  5 davidho davidho 4096 Mar 15 07:05 src
    -rw-rw-r--  1 davidho davidho   30 Mar 15 07:05 settings.gradle
    -rwxrw-r--  1 davidho davidho 2375 Mar 15 07:05 grailsw.bat
    -rwxrw-r--  1 davidho davidho 4672 Mar 15 07:05 grailsw
    -rw-rw-r--  1 davidho davidho 5507 Mar 15 07:05 grails-wrapper.jar
    -rw-rw-r--  1 davidho davidho   94 Mar 15 07:05 .gitignore
    drwxrwxr-x 12 davidho davidho 4096 Mar 15 07:05 grails-app
    -rw-------  1 davidho davidho  191 Mar 15 07:05 gradle.properties
    -rw-------  1 davidho davidho 4702 Mar 15 07:05 build.gradle
    drwxrwxr-x  5 davidho davidho 4096 Mar 15 07:05 .
    davidho@dphxps17:~/grailsprojs/prezinfo$ 
    davidho@dphxps17:~/grailsprojs/prezinfo$ tree -d
    .
    ├── gradle
    │   └── wrapper
    ├── grails-app
    │   ├── assets
    │   │   ├── images
    │   │   │   └── skin
    │   │   ├── javascripts
    │   │   └── stylesheets
    │   ├── conf
    │   │   └── spring
    │   ├── controllers
    │   │   └── prezinfo
    │   ├── domain
    │   ├── i18n
    │   ├── init
    │   │   └── prezinfo
    │   ├── services
    │   ├── taglib
    │   ├── utils
    │   └── views
    │       └── layouts
    └── src
        ├── integration-test
        │   ├── groovy
        │   └── resources
        ├── main
        │   ├── groovy
        │   └── webapp
        └── test
            └── groovy

    30 directories
    davidho@dphxps17:~/grailsprojs/prezinfo$ 

still more documentatio ...


This project implements four basic functions of connection pool based on C++17,
namely, initial connection volume, maximum connection volume, maximum idle time and connection timeout.

precondition：

  1. The project needs to include mysql data services, and create the chatp database and user data table, creating sql statements as follows:
  database： 
          create databases chatp；
  table：
          create table user(
          id int(11) primary key not null auto_increment,
          name varchar(50) not null,
          age int(11) not null,
          sex enum('M','W') not null
          );
          
  2. You can also modify the database and table names in the configuration files mysql.ini and main.cpp.
  
  3. In the configuration file mysql.ini, you also need to change your database login user and password.

Compile step:

One-click compilation ./autobuild.sh

By modifying the amount of data in main.cpp, you can achieve the purpose of stress testing.


Pressure measurement data：

  Data size         Time not spent using the connection pool                    Using the connection pool takes time
  1000           single thread：4630000ms  four-thread：5360000ms            single thread： 80000ms   four-thread：80000ms
  5000           single thread：22870000ms four-thread：26990000ms           single thread： 210000ms  four-thread：210000ms
  10000          single thread：45700000ms four-thread：53820000ms           single thread： 360000ms  four-thread：370000ms


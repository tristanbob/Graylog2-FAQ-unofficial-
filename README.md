DocumtenationTest
=================

How can I tell if Graylog2-server is running?

tristanrhodes@graylog2:~$ sudo service graylog2-server status
graylog2-server start/running, process 20148

tristanrhodes@graylog2:~$ sudo netstat -lnp | grep "12900\|9000"
tcp        0      0 127.0.0.1:12900         0.0.0.0:*               LISTEN      20148/java
tcp        0      0 0.0.0.0:9000            0.0.0.0:*               LISTEN      27056/java

tristanrhodes@graylog2:~$ tail -F /var/log/graylog2-server/server.log

How can I tell if Graylog2-web is running?

tristanrhodes@graylog2:~$ sudo service graylog2-web status
graylog2-web start/running, process 27056

tristanrhodes@graylog2:~$ sudo netstat -lnp | grep 9000
tcp        0      0 0.0.0.0:9000            0.0.0.0:*               LISTEN      27056/java

tristanrhodes@graylog2:~$ tail -F /var/log/graylog2-web/application.log

How can I tell if Mongodb is running?

tristanrhodes@graylog2:~$ sudo service mongod status
 * Checking status of database mongod                                                                                                                                                                                                 [ OK ]
tristanrhodes@graylog2:~$ sudo netstat -lnp | grep 27017
tcp        0      0 127.0.0.1:27017         0.0.0.0:*               LISTEN      890/mongod
unix  2      [ ACC ]     STREAM     LISTENING     7864     890/mongod          /tmp/mongodb-27017.sock

tristanrhodes@graylog2:~$ tail -F /var/log/mongodb/mongod.log

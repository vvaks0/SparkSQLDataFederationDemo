# SparkSQL Data Federation Demo

Demonstrate how SparkSQL can act as a distributed data federation platform. 

Tables are created from three different sources:

- Data that being processed by Spark
- Data in Hive
- Data in Postgres

Spark makes all of these tables available via JDBC as if from as single data store

# Getting Started

Download and Import Hortonworks Sandbox 2.4 for Virtual Box. Should work with VMWare but has not been tested. Modify local hosts file so that sandbox.hortonworks.com resolves to 127.0.0.1

Start Sandbox, SSH to Sandbox (ssh root@sandbox.hortonworks.com -p 2222)

Wait for Sandbox to fully boot up, all service need to finish starting

Change Ambari password 

`ambari-admin-password-reset` 

Use the /root directory to begin the install
'cd /root' 

`git clone https://github.com/vakshorton/SparkSQLDataFederationDemo.git`
`cp -rvf SparkSQLDataFederationDemo/Zeppelin/notebook/* /usr/hdp/current/zeppelin-server/lib/notebook/`

Zeppelin must be able to sudo and access Postgres. 
Run the following commands as root at the host console:

`echo "zeppelin ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers `
`echo "host all all 127.0.0.1/32 md5" >> /var/lib/pgsql/data/pg_hba.conf`

Log into Amabri as admin and restart the Zeppelin service

[http://sandbox.hortonworks.com:8080](http://sandbox.hortonworks.com:8080)


Access The Zeppelin Notebook

[http://sandbox.hortonworks.com:9995](http://sandbox.hortonworks.com:9995)
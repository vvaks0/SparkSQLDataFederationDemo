# SparkSQL Data Federation Demo

Demonstrate how SparkSQL can act as a distributed data federation platform. 

Tables are created from three different sources:

- Data that being processed by Spark
- Data in Hive
- Data in Postgres

Spark makes all of these tables available via JDBC as if from as single data store

# Getting Started

Zeppelin must be able to sudo and access Postgres. 
Run the following commands as root at the host console:

`echo "zeppelin ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers `
`echo "host all all 127.0.0.1/32 md5" >> /var/lib/pgsql/data/pg_hba.conf`
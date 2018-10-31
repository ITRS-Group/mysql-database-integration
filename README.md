# MySQL Database Monitoring

Initial commit based on a combination of the original useful-script and local changes.

The XML include file should be useable read-only.

Requirements:

* MySQL or MariaDB client installation and environment set-up so that the Netprobe will load SQL-Toolkit
* Default variables in the include file do not include a password for the user and in the general case all should be
  overriddenwhen attached to a Managed Entity
  
Variables Used:

MySQL-Status config variables:

MYSQL_DB_SERVER - Server hostname/IP. Default localhost
MYSQL_DB_PORT - Database port. Default 3306
MYSQL_DB_USER - Database user with permissions to issue status queries. Default "geneos"
MYSQL_DB_PASS - Password for above user. REQUIRED and no default set.
MySQL_DB_NAME - Database instance name. Default "geneos_db"
MYSQL_STATUS_SAMPLE_INTERVAL - Sample interval. Default 60 seconds.

MySQL-Status extra headlines:

Extra computed headlines are defined as string lists. This allows the user to add their own while using the XML file as read-only. If you change these you should copy the defaults over to retain default summary headlines. You can also remove them to stop computed rules from running.

MYSQL_STATUS_GLOBAL_HEADLINES - For the "Global Status" dataview. Default [ "cacheHitRate", "cacheInsertRate", "cachePruneRate" ]
MYSQL_STATUS_VARIABLES_HEADLINES - For the "Variables" dataview. Default [ "serverVersion" ]

MySQL Log File Monitoring:

MYSQL_LOGFILE - Location of readable server logfile. Sampler disabled as log file format varies too much.
MYSQL_SLOW_QUERIES_LOGFILE - Location of readable long queries log. Sampler disabled and provided as an example. Long Query logs must be enabled in the server config.



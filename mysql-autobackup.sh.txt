vim auto_backup_mysql.sh

#!/bin/bash
Backup_Location = /data/backup/ `date +% Y% m% d`
DB=gotipath 
USER=root 
PASS=123456  

#Mysql Backup command

mysqldump -u$USER -p$PASS -d $DB >$Backup_Location/MYSQLDB.sql


# add crontab -e for Daily 1:00 am backup

0 1 * * * /bin/bash /root/auto_backup_mysql.sh >>/tmp/mysql_bak.log

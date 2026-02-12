
# DB2 Configuration

### Author: Jawahar

## Create Database B3BI

Login into the machine as db2inst1 user.

```CMD
db2 CREATE DATABASE B2BI AUTOMATIC STORAGE YES USING CODESET UTF-8 TERRITORY DEFAULT COLLATE USING SYSTEM PAGESIZE 32768
```

## Modify DB2 Settings

```CMD
db2 connect to B2BI
```
```CMD
db2 update db cfg for B2BI using LOGFILSIZ 2048
```
```CMD
db2 update db cfg for B2BI using LOGPRIMARY 26
```
```CMD
db2 update db cfg for B2BI using LOGSECOND 24
```

## Restart DB2

```CMD
./db2stop force
```
```CMD
db2start
```
```CMD
exit
```

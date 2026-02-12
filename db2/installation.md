# DB2 Installation

### Author: Jawahar

## Installing DB2

Download the relevant version of DB2.**

In this setup the version used is **DB2_Svr_11.5_Linux_x86-64.tar.gz** <br>
Download [here](https://w3.ibm.com/software/xl/download/ticket.wss):<br>
part number: **CC1U0ML**

Copy the compressed file to the machine where it need to be installed as root user.

In this example it is moved to **/root/installables/db2/DB2_Svr_11.5_Linux_x86-64.tar.gz**

**3. Configure the db2server.rsp file**

Refer the db2server.rsp file in the following link:<br>
[db2server.rsp](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/db2/db2server.rsp)

**4. DB2 installation.**

Login as root.

Navigate to the binaries.

```CMD /root/installables/db2/
```

explode the compressed file and begin installation.

```CMD
tar -xvf DB2_Svr_11.5_Linux_x86-64.tar.gz
```
```CMD
cd server_dec/
```
Create a file called db2server.rsp. Sample file is available [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/db2/db2server.rsp). Modify as required. <br>


```CMD
./db2setup -r /root/installables/db2/server_dec/db2server.rsp -f sysreq
```
If successfully installed the following message will appear.

```TXT
DBI1191I  db2setup is installing and configuring DB2 according to the
      response file provided. Please wait.
The execution completed with warnings.
For more information see the DB2 installation log at "/tmp/db2setup.log".
[root@machine1 server_dec]#
```
Check the mentioned log for more details.

You should see the following:

```TXT
Initializing instance list :.......Success 
The instance "db2inst1" has been created successfully.

The value "SVCENAME=db2c_db2inst1" was set in the DBM CFG file for the
"db2inst1" instance.

The value "DB2AUTOSTART=YES" was set in the Profile Registry for the "db2inst1"
instance.

Configuring DB2 instances :.......Success 
Registering DB2 Update Service :.......Success 
Updating global profile registry :.......Success
```

**Check version**
Login to the machine as db2inst1

```CMD
db2level
```

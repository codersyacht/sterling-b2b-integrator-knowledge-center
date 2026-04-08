# IBM Sterling B2B Integration

### Author: Jawahar

## Prerequisite

Set system time to UTC. Follow instruction [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/system/system-time.md)

Set system locale to en_UTC. Follow instruction [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/system/locale.md)

Create non-root user, admin. Follow instructions [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/system/create-user.md)

Install DB2. Follow instruction [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/db2/installation.md)

Configure DB. Follow instructions [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/db2/configuration.md)

Install Java 17. Follow instruction [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/system/java-installation.md)


## Sterling B2B Integrator Installation

Download the Sterling B2B Integrator.

Download [here](https://w3.ibm.com/software/xl/download/ticket.wss)
part number: M0Y4ZML

Copy the compressed file to the machine where it need to be installed as admin user. Copy it to /home/admin/installables/sb2bi.

Login to the machine ad admin user.

Navigate to the directory containing the binaries.

```CMD
cd /home/admin/installables/sb2bi
```

Extract the binaries.
```CMD
unzip Media_IM_6020200.zip
```


### Install IBM Installation Manager

To install the IBM Installation Manager, follow the instructions [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/system/installation-manager.md)

### Encrypt DB and Sterling B2B admin password.

Navigate to /home/admin/apps/IM/eclipse/tools

```CMD
cd /home/admin/apps/IM/eclipse/tools
```
Execute the following command:

```CMD
./imutilsc encryptString LabMachine4@Training

Output:
```
```
65ftczCjjtIyrr+pc65aULyv9/PxaZ4SzqqA5NzJNmk=
```

### Install Sterling B2B Integrator

Download the Sterling B2B Integrator installation response file from [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/installation/responseFile_B2Bi.xml)

Review the file and make modification as required. Note that the encrypted password used in the previous step will be used in the response file. If you want to use a different password, regenrate the encrypted password for a password of your cchoice and use it instead in the response file.

Copy the file into /home/admin/installables/sb2bi/responseFile_B2Bi.xml

Navigate to /home/admin/apps/IM/eclipse/tools

```CMD
cd /home/admin/apps/IM/eclipse/tools
```
Execute the following command to begin installing IBM Sterling B2B Integrator.

```CMD
./imcl -input /home/admin/installables/sb2bi/responseFile_B2Bi.xml -acceptLicense 
```


## Start Sterling B2B Integrator and Launch Console

After the installation is complete, follow the below steps to start the Sterling B2B Integrator and access the web console.

### Start DB2 database

Switch to the db2inst1 user and start the DB2 database:

```CMD
su - db2inst1
db2start
exit
```

Expected Output : 
```CMD 
SQL1063N DB2START processing was successful.
```

### Configure Port Forwarding in Termius

In Termius, navigate to **Vaults → Port Forwarding → New Forwarding**

Add a new rule with the following specifications:
* Type: Local
* Local port number: 33700
* Destination address: localhost
* Destination port: 33700

Save the following rule and enable it.

Connect to the server, if already connected then reconnect. This will activate port forwarding.

### Start Sterling B2B Integrator

Navigate to the Sterling B2B bin directory and start the application:
```CMD 
cd /home/admin/apps/b2bi/bin
./run.sh
```

If you face any error about existing PID files run:

```CMD 
./hardstop.sh
./run.sh
```

Enter the passphrase when prompted.

### Verify Console Ready

Run the below command to verify that it's responding:

```CMD 
curl -s -I http://localhost:33700/dashboard/ | head -1
```

Expected output : `HTTP/1.1 200 OK`

### Access dashboard

Navigate to http://localhost:33700/dashboard/

The Sterling B2B Integrator Login dashboard should be visible, login with the default credentials.

**Default login credentials:**
- Username: `admin`
- Password: `password`

On first login, you'll be prompted to change the password. 

After successful password reset you will be redirected to the Sterling B2B Integrator Dashboard.

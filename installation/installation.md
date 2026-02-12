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
part number: G0GX3ML

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

To install the IBM Installation Manager, follow the instructions [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/db2/installation.md)

### Install Sterling B2B Integrator

Encrypt DB and Sterling B2B admin password.

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
```

Download the Sterling B2B Integrator installation response file from [here](https://github.com/codersyacht/sterling-b2b-integrator-knowledge-center/blob/main/installation/responseFile_B2Bi.xml)

Review the file and make modification as required.

Copy the file into /home/admin/installables/sb2bi/responseFile_B2Bi.xml

Navigate to /home/admin/apps/IM/eclipse/tools

```CMD
cd /home/admin/apps/IM/eclipse/tools
```
Execute the following command to begin installing IBM Sterling B2B Integrator.

```CMD
./imcl -input /home/admin/installables/sb2bi/responseFile_B2Bi.xml -acceptLicense 
```

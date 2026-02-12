# Installing IBM Installation Manager

### Author: Jawahar

Login as admin user.

Navigate to Installation Mnnager directory.

```CMD
cd /home/admin/installables/sb2bi/InstallationManager
```
```CMD
unzip IM_Linux.zip
```
```CMD
cd  IM_Linux
```

## Installation

```CMD
userinstc -installationDirectory /home/admin/apps/IM -acceptLicense
```

Note: Administrative directory will be present in /home/admin/opt/ibm

## Uninstallation (Optional)

Follow the instruction below only to perform uninstallation of the IBM Installation Manager.

```CMD
/home/<user>/var/ibm/InstallationManager/uninstall/uninstallc
```
Note: Before uninstallation ensure to remove all the installed products using the installation manager. Can be performed by removing the profile from the installRegistry.xml and location from the installed.xml.
These files can be found under /home/<user>/var/ibm/InstallationManager

**3. Logs:**
Logs related to IBM installation manager and other product installation logs can be found under:
/home/<user>/var/ibm/InstallationManager/logs

**4. To install product in interactive console mode:**
```CMD
./imcl –c
```
The command can be found under /home/admin/IBM/IM/eclipse/tools

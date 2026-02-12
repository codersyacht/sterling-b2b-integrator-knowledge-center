# Create User

## Create user admin

```CMD
useradd admin
```
```CMD
passwd admin
```

### Provide root access to admin user

Type **visudo** and edit the file by adding the following line under "_Allow root to run any commands anywhere_".

```script
admin    ALL=(ALL)   ALL
```
```
## Allow root to run any commands anywhere 
root     ALL=(ALL)   ALL
admin    ALL=(ALL)   ALL
```

Uncomment the following:

```
## Same thing without a password
%wheel  ALL=(ALL)       NOPASSWD: ALL
```

exit visudo.

### Add the user to wheel group

The wheel group is a special user group used to control access to the su or sudo command, which allows a user to masquerade as another user (usually the super user).

```CMD
sudo usermod -aG wheel admin
```
Exit and login back as admin user.


### Check a user in a group

```script
groups <user>
```

### Check all users in a group

```script
getent group <group>
```

Exit and login back as **admin**.

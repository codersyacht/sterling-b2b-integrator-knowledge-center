# Setting the Locale

### Author: Jawahar

## Editing the Locale 

```CMD
sudo vi /etc/locale.conf
```

Replace content with:
```
LANG=en_US
LC_ALL=en_US
```

Apply Changes:
```
source /etc/locale.conf
```

Check the settings:
```
localectl status
```

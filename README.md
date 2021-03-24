# AEM Services

Just a set of simple services to use to start/stop an AEM OSGi server.

## systemd

Make sure your user is part of the `systemd-journal` or a sudoer and then copy the *.service files to `/etc/systemd/system`. Once the files are located in that folder then perform the following actions

1. sudo systemctl enable aem-author.service
2. sudo systemctl enable aem-publish.service
3. sudo systemctl start aem-author.service
4. sudo systemctl start aem-publish.service

Check your log files to make sure that the service is starting correctly, if it is not working correctly then check the `journalctl` log file for any errors.

```
sudo journalctl -u aem-author.service
sudo journalctl -u aem-publish.service
```

**Note**: Make sure to update the following properties
1. Description
2. User
3. ExecStart
4. ExecStop

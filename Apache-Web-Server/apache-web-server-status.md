# Apache Web server in Ubuntu 

## checking apache web server status using `systemd` command
`sudo systemctl status apache2`

```
apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor prese>
     Active: active (running) since Thu 2023-09-28 09:53:48 IST; 1min 17s ago
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 5604 (apache2)
      Tasks: 55 (limit: 4416)
     Memory: 5.4M
        CPU: 64ms
     CGroup: /system.slice/apache2.service
             ├─5604 /usr/sbin/apache2 -k start
             ├─5605 /usr/sbin/apache2 -k start
             └─5606 /usr/sbin/apache2 -k start

Sep 28 09:53:48 ASUS-SAF systemd[1]: Starting The Apache HTTP Server...
Sep 28 09:53:48 ASUS-SAF apachectl[5603]: AH00558: apache2: Could not reliably >
Sep 28 09:53:48 ASUS-SAF systemd[1]: Started The Apache HTTP Server.
```

## If it is running, stop it and check again. 
`sudo systemctl stop apache2`

`sudo systemctl status apache2`

```
apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor prese>
     Active: inactive (dead) since Thu 2023-09-28 09:57:16 IST; 4s ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 6346 ExecStop=/usr/sbin/apachectl graceful-stop (code=exited, stat>
   Main PID: 5604 (code=exited, status=0/SUCCESS)
        CPU: 120ms

Sep 28 09:53:48 ASUS-SAF systemd[1]: Starting The Apache HTTP Server...
Sep 28 09:53:48 ASUS-SAF apachectl[5603]: AH00558: apache2: Could not reliably >
Sep 28 09:53:48 ASUS-SAF systemd[1]: Started The Apache HTTP Server.
Sep 28 09:57:16 ASUS-SAF systemd[1]: Stopping The Apache HTTP Server...
Sep 28 09:57:16 ASUS-SAF apachectl[6348]: AH00558: apache2: Could not reliably >
Sep 28 09:57:16 ASUS-SAF systemd[1]: apache2.service: Deactivated successfully.
Sep 28 09:57:16 ASUS-SAF systemd[1]: Stopped The Apache HTTP Server.
```

## Start the service and check the status. 
`sudo systemctl start apache2`

`sudo systemctl status apache2`

```
apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor prese>
     Active: active (running) since Thu 2023-09-28 09:59:51 IST; 3s ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 6370 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SU>
   Main PID: 6374 (apache2)
      Tasks: 55 (limit: 4416)
     Memory: 5.0M
        CPU: 42ms
     CGroup: /system.slice/apache2.service
             ├─6374 /usr/sbin/apache2 -k start
             ├─6375 /usr/sbin/apache2 -k start
             └─6376 /usr/sbin/apache2 -k start

Sep 28 09:59:51 ASUS-SAF systemd[1]: Starting The Apache HTTP Server...
Sep 28 09:59:51 ASUS-SAF systemd[1]: Started The Apache HTTP Server.
Sep 28 09:59:51 ASUS-SAF apachectl[6373]: AH00558: apache2: Could not reliably >
```

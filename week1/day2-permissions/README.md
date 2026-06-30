\# Day 2: File Permissions



\## What this lab covers

Understanding and applying Linux file permissions — chmod, chown, and 

realistic permission patterns used on production servers.



\## Commands I practised

```bash

ls -la \~/labs/web-app/config/

chmod 640 \~/labs/web-app/config/app.conf

chmod 775 \~/labs/web-app/logs/app/

sudo useradd -m webuser

sudo chown webuser:webteam \~/labs/web-app/config/app.conf

```



\## Screenshot

!linux-ops-labs/week1/day2-permissions/screenshots/




\## What I learned

\- chmod 640 = owner read/write, group read, others nothing — used for config files

\- chmod 775 = owner/group full access, others read/execute — used for shared directories

\- chown changes both owner and group in one command using `owner:group` syntax



\## Real-world use case

When a cloud support ticket says "application can't read its config file," 

checking `ls -la` on the file and comparing the permission bits to what the 

running service user needs is often the fastest fix.



\## What broke and how I fixed it

intentionally removed the Read (r) permission for the Owner (u) of the configuration file.
locked the owner out of their own file. When the webuser tried to look at the file using cat, Linux blocked it and threw a "Permission denied" error.
for fixing it gave the Read (r) permission back to the Owner (u).
Access was instantly restored, allowing the webuser to read the configuration file again.


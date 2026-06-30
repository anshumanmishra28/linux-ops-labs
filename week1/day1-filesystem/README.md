\# Day 1: Filesystem Navigation



\## What this lab covers

Practiced Linux filesystem navigation and structure creation — building 

nested directories, creating files with content, and using symlinks.



\## Commands I practised

```bash

mkdir -p \~/labs/web-app/{config,logs,scripts,data}

mkdir -p \~/labs/web-app/logs/{access,error,app}

find \~/labs -type d | sort

echo "\[$(date)] Server started" > \~/labs/web-app/logs/app/startup.log

ln -s \~/labs/web-app/logs \~/labs/log-shortcut

```



\## Screenshot

!Present in my day - 1 (linux-ops-labs/week1/day1-filesystem/screenshots/)

\## What I learned

\- `mkdir -p` with `{}` brace expansion creates multiple nested folders in one command

\- `find -type d` lists only directories, useful for verifying structure

\- Symlinks (`ln -s`) point to another location without duplicating data



\## Real-world use case

Cloud support engineers often need to quickly verify a deployment's expected 

folder structure exists on a server, or create config/log directory layouts 

when setting up a new application server.



\## What I'd do differently

Sometimes i stuck in between then i fix errors by reading the error message and i was calm and compose throughout the lab 


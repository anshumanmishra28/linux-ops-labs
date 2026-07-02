Day 3: Process and Service Management



What this lab covers



Practiced installing and managing a real web server (Nginx) on CentOS, investigating running system processes, sending termination and reload signals, and managing background vs. foreground jobs.



Commands I practised



sudo dnf install -y nginx

sudo systemctl start nginx

sudo systemctl status nginx

ps aux | grep nginx

pgrep -a nginx

sudo kill -SIGHUP $(pgrep -f "nginx: master process")

sudo kill -9 $(pgrep -f "nginx: master process")

sleep 300 \&

jobs

fg %1





Screenshot



What I learned



dnf is the package manager for CentOS/Red Hat, whereas apt is for Ubuntu/Debian.



systemctl is the central command used to start, stop, and check the health of background services.



kill -SIGHUP gracefully reloads a configuration without dropping users, while kill -9 (SIGKILL) forces a hard, immediate termination.



Adding an ampersand (\&) to the end of a command sends it to run in the background, keeping the terminal free for other work.



Real-world use case



Cloud support engineers and sysadmins constantly rely on these commands to troubleshoot misbehaving applications. If a server is running out of memory, they use process investigation (top, ps) to find the culprit, and kill to terminate it. They also use graceful reloads (SIGHUP) to apply configuration changes to live production web servers without causing downtime for customers.



What I'd do differently



Initially I was slightly confused by why kill -9 put Nginx into a red "failed" state instead of just shutting it down cleanly. I realized kill -9 simulates a crash, and that I should use systemctl stop nginx if I actually want to cleanly turn off the service on purpose!


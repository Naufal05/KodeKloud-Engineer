With the installation of new tools on the app servers within the Stratos Datacenter, certain functionalities now necessitate graphical user interface (GUI) access.

Adjust the default runlevel on all App servers in Stratos Datacenter to enable GUI booting by default. It's imperative not to initiate a server reboot after completing this task.

SOLUTION

1. get into all the 3 servers
2. super use : sudo su - 

3. systemctl get-default
3. systemctl set-default graphical.target
4. check whether cheaged to graphical.target
    - systemctl get-default


---------------------------------------------------
Notes:
-----
systemctl is a command-line tool in Linux (on systems using systemd) that is used to:

Manage system services (start, stop, restart, enable, disable services)

Check the status of services

Manage system states (reboot, power off, etc.)

Inspect logs and configuration for services
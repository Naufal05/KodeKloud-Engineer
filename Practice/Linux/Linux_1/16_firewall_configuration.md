The Nautilus system admins team has rolled out a web UI application for their backup utility on the Nautilus backup server within the Stratos Datacenter. This application operates on port 8088, and firewalld is active on the server. To meet operational needs, the following requirements have been identified:


Allow all incoming connections on port 8088/tcp. Ensure the zone is set to public.

SOLUTION

1. check if hte firewall is running:
    - sudo systemctl status firewalld

    Look for Active: active (running).

2.  List all active firewall rules
    - sudo firewall-cmd --list-all

3. . Check permanent rules (saved configuration)
    - sudo firewall-cmd --list-all --permanent

4. Displays rules for every configured zone.
    - sudo firewall-cmd --list-all-zones

5. run the following command to open port and set the zone to public
    - sudo firewall-cmd --zone=public --add-port=8089/tcp --permanent

This command adds a rule to the public zone of firewalld, allowing incoming connections on port 8089/tcp. The --permanent flag ensures that the rule persists across system reboots.

To check if the firewall rule allowing incoming connections on port 8088/tcp has been successfully applied, you can perform the following steps:

1. curl http://172.16.238.16:8088 If you receive a response or see the web UI, it indicates that the firewall rule is allowing incoming connections on port 8088/tcp.

2. or you can verify the status of the firewall rule on the Nautilus backup server by running the following command: sudo firewall-cmd --zone=public --list-ports
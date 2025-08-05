A Nautilus developer has stored confidential data on the jump host within Stratos DC. To ensure security and compliance, this data must be transferred to one of the app servers. Given developers lack direct access to these servers, the system admin team has been enlisted for assistance.



Copy /tmp/nautilus.txt.gpg file from jump server to App Server 1 placing it in the directory /home/appdata.

SOLUTION

1.  securely copy files between hosts on a network
scp /tmp/nautilus.txt.gpg tony@172.16.238.10:/home/appdata

2. ssh tony@172.16.238.10
    - cd /home/appdata
    - ls
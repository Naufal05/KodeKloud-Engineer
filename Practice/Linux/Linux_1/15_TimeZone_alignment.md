In the daily standup, it was noted that the timezone settings across the Nautilus Application Servers in the Stratos Datacenter are inconsistent with the local datacenter's timezone, currently set to Asia/Khandyga.

Synchronize the timezone settings to match the local datacenter's timezone (Asia/Khandyga).

SOLUTION
ssh into the App Server 1: ssh tony@172.16.238.10

ssh into the App Server 2: ssh steve@172.16.238.11

ssh into the App Server 3: ssh banner@172.16.238.12

Check the current timezone configuration: timedatectl show

Update the timezone setting: sudo timedatectl set-timezone America/Bogota

Verify the timezone synchronization: timedatectl show | grep Timezone

Note:
1. timeDatectl command

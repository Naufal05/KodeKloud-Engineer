In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 1 within the Stratos Datacenter.



Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 1. Additionally, ensure that all users have the capability to execute it.


Solution:
ssh into the App Server 1: ssh tony@172.16.238.10

Check files: cd /tmp

Change permissions: sudo chmod +rx xfusioncorp.sh

chmod: The command used to change file permissions.
+rx: The + sign grants the specified permissions, and r and x represent read and execute permissions, respectively. By using +rx, you are granting both read and execute permissions to the file.
file_name: The name of the file you want to modify the permissions for.
Note: To make a file executable, it must also be readable.

Check the result: ls -l xfusioncorp.sh

image

In this case, the owner has read and execute permissions, while the group and other users have read and execute permissions as well. This means that all users (owner, group, and others) can read and execute the file.
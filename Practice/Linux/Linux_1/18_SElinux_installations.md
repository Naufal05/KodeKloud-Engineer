Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. To initiate testing, the following requirements have been established for App server 1 in the Stratos Datacenter:

1. Install the required SELinux packages.

2. Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.

3. No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.

4. Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.


SOLUTION

1. ssh into the App Server 1: ssh tony@172.16.238.10

2. Run the following command to update the package manager and ensure you have the latest package information:
    - sudo yum update

3. Install the required SELinux packages by running the following command:
    - sudo yum install selinux-policy selinux-policy-targeted

4. To disable SELinux permanently, you need to modify the SELinux configuration file:
    - sudo vi /etc/selinux/config

    Change SELINUX=enforcing to SELINUX=disabled

Check the status: sestatus

You should see: SELinux status: disabled


Note:
------
On a Linux system, you generally require a package manager for any process that involves:
1. installing
2.  Updating 
3. Removing software
4.  Managing package dependencies
1.

After conducting comprehensive security audits on its servers, xFusionCorp Industries security team has instituted several new security measures. Among these measures is the discontinuation of direct root login through SSH.

Disable direct SSH root login across all application servers located in the Stratos Datacenter.


1. ssh to the server
2. vi: sudo vi /etc/ssh/sshd_config
    -PermitRootLogin to no

3. Restart the ssh-deamon
    - sudo systemctl restart sshd

--------------------------------------------------------------------------

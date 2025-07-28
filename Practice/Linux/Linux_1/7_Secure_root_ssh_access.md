<!-- Test -->
Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.



Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

Solution

<!-- Step 1 -->
ssh into the App Server 1: ssh tony@172.16.238.10

ssh into the App Server 2: ssh steve@172.16.238.11

ssh into the App Server 3: ssh banner@172.16.238.12


<!-- Step 2 -->
Open the SSH server configuration file (usually located at /etc/ssh/sshd_config) using a text editor such as v
- sudo vi /etc/ssh/sshd_config

Modify the value of PermitRootLogin to no or without-password. This disables direct root login.

Setting it to no will completely disable root login.
Setting it to without-password will allow root login only with public key authentication.
<!-- Step 3 -->
Restart the SSH server daemon (sshd) sudo systemctl restart sshd

- sudo systemctl restart sshd

to check the status 
- sudo systemctl status sshd,

---------------------------------------------------------
<!-- Additional notes for reference -->
After modifying /etc/ssh/sshd_config and setting PermitRootLogin no (or without-password), you need to verify that root login is disabled. Here are several ways to confirm:

✅ 1. Check the effective SSH configuration
Run:

bash
Copy
Edit
sudo sshd -T | grep permitrootlogin
This command shows the current active configuration.

If it outputs:

nginx
Copy
Edit
permitrootlogin no
then root login is disabled.

✅ 2. Test SSH root login
Try to SSH as root from the same machine or another system:

bash
Copy
Edit
ssh root@localhost
You should receive a "Permission denied" message if root login is disabled.

✅ 3. Check the sshd_config file
Manually verify the line in /etc/ssh/sshd_config:

bash
Copy
Edit
grep -i permitrootlogin /etc/ssh/sshd_config
Ensure it is set to:

nginx
Copy
Edit
PermitRootLogin no
and not commented out (#).

✅ 4. Verify through logs
Attempt a root login and check logs:

bash
Copy
Edit
sudo journalctl -u sshd | tail -n 20
or

bash
Copy
Edit
sudo cat /var/log/auth.log | grep sshd
You should see messages like "root login refused".

✔️ Remember to restart SSH after modifying the file:

bash
Copy
Edit
sudo systemctl restart sshd
💡 Quickest way:
Run sshd -T | grep permitrootlogin — if it says no, root login is successfully disabled.
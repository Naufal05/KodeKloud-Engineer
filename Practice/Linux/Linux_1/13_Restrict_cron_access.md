In alignment with security compliance standards, the Nautilus project team has opted to impose restrictions on crontab access. Specifically, only designated users will be permitted to create or update cron jobs.



Configure crontab access on App Server 1 as follows: Allow crontab access to kareem user while denying access to the ryan user.

SOLUTION

1. ssh tony@172.16.238.10
2. sudo su
3. cat /etc/passwd
    - lists all user accounts on the system.

4. echo kareem >> /etc/cron.allow
5. echo ryan >> /etc/cron.deny

6. after the changes, restart and check the statusof the cron.service
- sudo systemctl restart crond.service

- sudo systemctl status crond.service

7. cat /etc/cron.deny  and cat /etc/cron.allow

This command will display the crontab entries for the "rose" user. If the user has any cron jobs set up, you will see them listed in the output:
- sudo crontab -u kareem -l (in our case no cron jobs)
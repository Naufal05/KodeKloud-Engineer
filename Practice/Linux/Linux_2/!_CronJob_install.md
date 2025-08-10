The Nautilus system admins team has prepared scripts to automate several day-to-day tasks. They want them to be deployed on all app servers in Stratos DC on a set schedule. Before that they need to test similar functionality with a sample cron job. Therefore, perform the steps below:



a. Install cronie package on all Nautilus app servers and start crond service.


b. Add a cron */5 * * * * echo hello > /tmp/cron_text for root user.

SOLUTION

1. ssh to the server

2. sudo yum install cronie

3. sudo systemctl start crond

4. sudo systemctl status crond

5. Open the crontab editor for the root user by executing the following command:
    - sudo crontab -e -u root


    In the crontab editor, add the following line: */5 * * * * echo hello > /tmp/cron_text

Then open /tmp/ after 5min the file will appear there
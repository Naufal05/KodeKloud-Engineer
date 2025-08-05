DevOps team created a new Git repository last week; however, as of now no team is using it. The Nautilus application development team recently asked for a copy of that repo on Storage server in Stratos DC. Please clone the repo as per details shared below:

The repo that needs to be cloned is /opt/beta.git
Clone this git repository under /usr/src/kodekloudrepos directory. Please do not try to make any changes in the repo.

Solution

1. ssh into the Nautilus Storage Server: ssh natasha@172.16.238.15

2. check  the git repo in /opt

3. cd to cd /usr/src/kodekloudrepos

4. sudo git clone /opt/beta.git /usr/src/kodekloudrepos/beta
    - make ure you add the name atthe end

5. ls -l
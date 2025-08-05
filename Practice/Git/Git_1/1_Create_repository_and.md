The Nautilus development team has provided requirements to the DevOps team for a new application development project, specifically requesting the establishment of a Git repository. Follow the instructions below to create the Git repository on the Storage server in the Stratos DC:

1. Utilize yum to install the git package on the Storage Server.

2. Create a bare repository named /opt/games.git (ensure exact name usage).


SOLUTION

1. ssh into the Nautilus Storage Server: ssh natasha@172.16.238.15

2. update the package manager's cache
    - sudo yum update

3. an install git by running the following command
    - sudo yum install git
    - git --version

4. Change the current directory to the /opt directory: cd /opt

5. git init --bare gmaes.git

7.  ls -l // the /opt folder -lisitng the contents of the /opt


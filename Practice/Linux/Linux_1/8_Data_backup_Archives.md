Within the Stratos DC, the Nautilus storage server hosts a directory named /data, serving as a repository for various developers non-confidential data. Developer mariyam has requested a copy of their data stored in /data/mariyam. The System Admin team has provided the following steps to fulfill this request:



a. Create a compressed archive named mariyam.tar.gz of the /data/mariyam directory.

b. Transfer the archive to the /home directory on the Storage Server.


SOLUTION

1. SSH to the Storage server
    - ssh natasha@172.16.238.15


2. check file in the /data/mariyam
    - ls -ld /data/mariyam
    - cd /data/mariyam

3. compress the file
    - tar -czvf mariyam.tar.gz /data/mariyam

    -c: Create a new archive.
-z: Compress the archive using gzip.
-v: Verbose mode, display the progress and details of the archiving process.
-f: Specify the name of the archive file.


4. Movve to home directory
    - sudo mv mariyam.tar.gz /home
5. Check
    - ls /home  // lists all the items in te home directory
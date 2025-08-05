On our Storage server in Stratos Datacenter we are having some issues where nfsuseruser is holding hundred of processes, which is degrading the performance of the server. Therefore, we have a requirement to limit its maximum processes. Please set its maximum process limits as below:

a. soft limit = 1027

b. hard_limit = 2025



SOLUTION

1. ssh into the Storage server: ssh natasha@172.16.238.15

2. Edit the system limits configuration file: 
    
    sudo vi /etc/security/limits.conf

3.  nfsuser soft nproc 1027 
    nfsuser hard nproc 2025

4. to check the changes:

    - sudo su -c "su -c 'ulimit -Hu' -s /bin/sh nfsuser" 

    output : 2026


NOTES:
In the context of Linux system limits, nproc stands for:

✅ Number of Processes
It defines the maximum number of processes (tasks) that a particular user can create.

This is a per-user limit.

Why is nproc important?
Prevents a single user from creating too many processes and exhausting system resources (fork bomb protection).

Ensures fair resource allocation on multi-user systems.

--------------------------------------------------
On Linux, system limits (like maximum open files, processes, etc.) are configured through several files depending on what limit you are looking for.

✅ 1. Main System Limits Configuration File
- /etc/security/limits.conf
cat /etc/security/limits.conf


On Linux, system limits (like maximum open files, processes, etc.) are configured through several files depending on what limit you are looking for.

✅ 1. Main System Limits Configuration File
The primary configuration file is:

bash
Copy
Edit
/etc/security/limits.conf
Defines per-user and per-group resource limits.

Common limits set here include nofile (open files), nproc (processes), etc.

You can check it with:

bash
Copy
Edit
cat /etc/security/limits.conf
✅ 2. Additional Configuration Directory
In addition, limits may also be set in:

swift
Copy
Edit
/etc/security/limits.d/
This directory contains .conf files where system administrators can define custom limits without modifying the main limits.conf.

Example:

bash
Copy
Edit
ls /etc/security/limits.d/
✅ 3. PAM (Pluggable Authentication Module) Integration
For these limits to take effect, the PAM configuration file usually references them:

bash
Copy
Edit
/etc/pam.d/common-session
/etc/pam.d/common-session-noninteractive
Look for a line:

swift
Copy
Edit
session required pam_limits.so
✅ 4. System-Wide (Kernel) Limits
For kernel-level limits, check:

bash
Copy
Edit
/etc/systemd/system.conf
/etc/systemd/user.conf
These files include directives like:

makefile
Copy
Edit
DefaultLimitNOFILE=
DefaultLimitNPROC=
✅ 5. Temporary (Runtime) Limits
You can check current limits with:

bash
Copy
Edit
ulimit -a
These limits are session-based and not persistent.

💡 Summary:

1. Persistent per-user limits → /etc/security/limits.conf and /etc/security/limits.d/

2. Systemd service limits → /etc/systemd/system.conf

3. Runtime limits → use ulimit -a

👉 Do you also want me to show how to verify which limits are currently applied to a user or service?
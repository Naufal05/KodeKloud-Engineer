To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:



Create a user named kirsty with a non-interactive shell on App Server 1.


Solution

1.  ssh tony@172.16.238.10

2. sudo useradd --shell /bin/false kristy

3. to check the user exists:
    id krsity

🛡️ Why Create a Non-Interactive Shell?
A non-interactive shell means the user:

Can’t log in interactively (e.g., via SSH)

Can run scripts or commands if triggered indirectly (e.g., via cron, systemd, or automation tools)

Has restricted access, minimizing security risks

🔑 Common Use Cases
Use Case	Description
🔐 Security accounts	System users created for running specific services (e.g., nginx, mysql)
🤖 Automation users	Used by CI/CD tools or cron jobs — no shell access needed
📦 SFTP-only users	Restrict users to file transfer only — no shell access
🔒 Lock down system	Prevent login while keeping access to files or services

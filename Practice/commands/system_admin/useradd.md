. Use useradd --help (Quick Help)
📌 Command:
bash
Copy
Edit
useradd --help
This gives you a summary of available options. Here's an example snippet of what you'd see:

lua
Copy
Edit
Usage: useradd [options] LOGIN
Options:
  -b, --base-dir BASE_DIR       base directory for the home directory
  -c, --comment COMMENT         comment field (usually full name)
  -d, --home-dir HOME_DIR       home directory
  -D, --defaults                show or change default useradd configuration
  -e, --expiredate EXPIRE_DATE  set account expiration date
  -f, --inactive INACTIVE       set password expiration inactivity period
  -g, --gid GROUP               name or ID of the primary group
  -G, --groups GROUPS           list of supplementary groups
  -m, --create-home             create the user's home directory
  -M, --no-create-home          do not create home directory
  -N, --no-user-group           do not create a group with the same name
  -r, --system                  create a system account
  -s, --shell SHELL             login shell
  -u, --uid UID                 specify user ID
📖 Most Common useradd Options
Option	Description
-m or --create-home	Create a home directory
-M or --no-create-home	Don’t create a home directory
-s /path/to/shell	Set login shell (/bin/bash, /sbin/nologin)
-u	Set UID
-g	Set primary group
-G	Set supplementary groups
-d	Set custom home directory path
-c	Add a comment (usually full name)
-e	Set account expiration date
-f	Set inactivity days after password expiration
-r	Create a system user (used for services)

📌 Example
bash
Copy
Edit
sudo useradd -m -s /bin/bash -c "Anita Joseph" anita
This creates a user anita:

With a home directory

Using /bin/bash shell

Full name/comment: "Anita Joseph"


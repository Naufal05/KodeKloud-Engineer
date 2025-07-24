✅ Step 1: SSH into App Server 1
Use the provided credentials to log into the server:

ssh tony@172.16.238.10
(You may be prompted for a password if not using SSH keys.)

✅ Step 2: Become Superuser (if required)
Run the following to get root privileges (if needed):

sudo -i

✅ Step 3: Locate Files Owned by john (excluding directories)
Now run the find command to locate files owned by john inside /home/usersdata:

find /home/usersdata -type f -user john
This will list all files owned by john.

✅ Step 4: Copy These Files to /blog Preserving Directory Structure
Now use this command to copy the files with directory structure:

find /home/usersdata -type f -user john -exec cp --parents {} /blog \;
🔸 --parents flag ensures that the directory structure is preserved inside /blog.

✅ Step 5: (Optional) Verify
Check inside /blog to verify the files were copied with directory structure:

ls -R /blog

----------------------------------
The -R option in ls -R /blog stands for:

🔁 Recursive
It tells ls to:

List all subdirectories and their contents recursively.

Example:
If you run:

bash
Copy
Edit
ls -R /blog
You might see:

bash
Copy
Edit
/blog:
photos  reports

/blog/photos:
img1.jpg  img2.jpg

/blog/reports:
report1.txt  report2.txt
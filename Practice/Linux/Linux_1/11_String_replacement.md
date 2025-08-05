Within the Stratos DC, the backup server holds template XML files crucial for the Nautilus application. Before utilization, these files require valid data insertion. As part of routine maintenance, system admins at xFusionCorp Industries employ string and file manipulation commands.



Your task is to substitute all occurrences of the string Text with Submarine within the XML file located at /root/nautilus.xml on the backup server.


SOLUTION

1.Connect to the backup server
ssh clint@172.16.238.16

2. To check if the file exists, run this

sudo bash -c 'if [ -f /root/nautilus.xml ]; then echo "File exists."; else echo "File does not exist."; fi'

3. becomae super user
 sudo su -

4. Check all the lines in the "/root/nautilus.xml" file that include the word "Text"
cat /root/nautilus.xml  |grep Text

5. command to replace all occurrences of the string "Text" with "Submarine" in the XML file 

sed -i 's/About/Marine/g' nautilus.xml

- sed: A command-line tool for stream editing.
- i: Modifies the file in-place (i.e., edits the file directly).
- 's/About/Marine/g': The s command in sed is used for substitution. It replaces all occurrences of "About" with "Marine" in each line of the file. The g flag ensures that all occurrences are replaced, not just the first occurrence.
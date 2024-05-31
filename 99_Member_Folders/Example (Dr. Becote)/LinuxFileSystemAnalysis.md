# [Linux File System Analysis ](https://tryhackme.com/r/room/linuxfilesystemanalysis)
<img style= "float: center; width: 173px; height: 200px; margin: 5px;" src="https://github.com/Bbecote/UAT_Cyber_Competition_Team/assets/14898987/56adeee6-b460-4b9e-bc42-57b684c7d4e9"/> \
Platform: Try Hack Me\
Category: Walkthrough\
Concepts: Analyze Windows Drive\
Difficulty: Medium

## Walkthrough

1. To practice your skills with the find command, locate all the files that the user bob created in the past 1 minute. Once found, review its contents. What is the flag you receive? 
    1. I used the below command to find the /var/tmp/findme.txt
        1. ```find / -user bob -type f 2>/dev/null | less . ``` 
    2. I used the below command to output the flag
        1. ```cat /var/tmp/findme.txt```
2. Extract the metadata from the **`reverse.elf`** file. What is the file's MIME type?
    1. Using the following command indicated the MIME type
        1. ```exiftool /var/www/html/assets/reverse.elf```
3. Run the stat command against the /etc/hosts file on the compromised web server. What is the full Modify Timestamp (mtime) value?
    1. Using the following command indicated the full Modify Timestamp
        1. ```stat /etc/hosts```
4. Investigate the user accounts on the system. What is the name of the backdoor account that the attacker created?
    1. ```cat /etc/group```
5. What is the name of the group with the group ID of 46?
    1. ```cat /etc/group (same command as above, reference ID 46)```
6. View the /etc/sudoers file on the compromised system. What is the full path of the binary that Jane can run as sudo?
    1. ```sudo cat /etc/sudoers```
7. View Jane's **`.bash_history`** file. What flag do you see in the output? 
    1. THM{f38279ab9c6af1215815e5f7bbad891b}
    2. ```sudo cat /home/jane/.bash_history```
8. What is the hidden flag in Bob's home directory?
    1. THM{6ed90e00e4fb7945bead8cd59e9fcd7f}
    2. ```ls -a /home/bob displays 50 files…too many to search one at a time```
    3. ```sudo find /home/bob -type f -name ".hidden*" -exec grep -l 'THM*' {}``` \; displays all the files with the text THM
    4. ```sudo cat /home/bob/.hidden34```
9. Run the stat command on Jane's authorized_keys file. What is the full timestamp of the most recent modification?
    1. 2024-02-13 00:34:16.005897449 +0000
    2. ```stat /home/jane/.ssh/authorized_keys``` gives me the access, modify and change timestamps. Access is the was the most recent - the answer is incorrect in THM
10. Run the debsums utility on the compromised host to check only configuration files. Which file came back as altered?
    1. /etc/sudoers
    2. ```sudo debsums -e -s```
11. What is the md5sum of the binary that the attacker created to escalate privileges to root?
    1. 7063c3930affe123baecd3b340f1ad2c
    2. ```md5sum /var/tmp/bash```
12. Run chkrootkit on the affected system. What is the full path of the .sh file that was detected?
    1. /var/tmp/findme.sh
    2. ```sudo chkrootkit```
13. Run rkhunter on the affected system. What is the result of the (UID 0) accounts check?
    1. Warning
    2. ```sudo rkhunter -c -sk```

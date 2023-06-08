#### This repo contains solution to the Bandit Linux wargame found at : https://overthewire.org/wargames/bandit

The files numbered 0,1,2 etc contains the (password) which represents the solution at each level in the game.

The command for writing the password into the files:

- **echo <password) > (digit)**

The command for using these password files to ssh into the remote server:

- **sshpass -p $(cat digit) ssh bandit(n)@bandit.labs.overthewire.org -p 2220**

(password)  : The solution at each level
 digit      : Numerical value used as file-name
(n)         : Current level in the game


| Level    | Description                                                                 | Commands                                                                                                          |
|----------|-----------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| 1        | SSH Login                                                                   |                                                                                                                   |
| Level 2  | Read a File                                                                 | cat readme                                                                                                        |
| Level 3  | Unusually named Files                                                       | cat ./-                                                                                                           |
| Level 4  | Spaces in a filename                                                        | cat 'Spaces in a filename'                                                                                        |
| Level 5  | Hidden Files                                                                | ls -al \| cat .hidden                                                                                             |
| Level 6  | File types, specifically human-readable files.                              | for i in $(ls); do file ./$i; done    cat ./-file07                                                               |
| Level 7  | Human-readable files, file sizes and non-executable files                   | find . -readable -size 1033c -not -executable ;  cat ./inhere/maybehere07/.file2                                  |
| Level 8  | Find a file with specific user and group ownership                          | find / -user bandit7 -group bandit6 -size 33c 2>/dev/null ;  cat /var/lib/dpkg/info/bandit7.password              |
| Level 9  | Learning grep and piping                                                    | cat data.txt \| grep 'millionth'                                                                                  |
| Level 10 | Linux command uniq and sort, to find lines only appearing once.             | cat data.txt \| sort \|uniq -c \| grep -v 10                                                                      |
| Level 11 | The ‘strings’ command. Find human-readable strings in a file                | strings data.txt \| grep =                                                                                        |
| Level 12 | Base64                                                                      | cat data.txt \| base64 -d                                                                                         |
| Level 13 | Rot13 substitution cipher as Linux command with ’tr’                        | Use Rot13.com to decode the password                                                                              |
| Level 14 | Hexdumps and compression and file signatures.                               | xxd -r data.txt; Use gzip,bzip2 and tar to decompress resulting files until you get a  an ASCII text file         |
| Level 15 | SSH Login with key and transferring files from a remote host                | ssh bandit14@localhost -p 2220 -i sshkey.private ; cd /etc/bandit_pass/bandit14                                   |
| Level 16 | Netcat and first network communication                                      | nc localhost 30000                                                                                                |
| Level 17 | OpenSSL, secure communication                                               | openssl s_client -connect localhost:30001                                                                         |
| Level 18 | Find differences in a file.                                                 | diff passwords.old passwords.                                                                                     |
| Level 19 | Advanced SSH, remote command execution.                                     | sshpass -p $(cat 18) ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme                                  |
| Level 20 | Suid and linux permissions.                                                 | ./bandit20-do cat /etc/bandit_pass/bandit20                                                                       |
| Level 21 | Setuid binary, netcat and background processes/jobs.                        | Listen from terminal 1 nc -lvp<port_num>, establish connection from terminal2 using the provided suconnect script |
| Level 22 | Cronjobs.                                                                   | cat cronjob_bandit22 file , cat /usr/bin/cronjob_bandit22.sh  and cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv       |
| Level 23 | Cronjobs.                                                                   | myname=bandit23, echo I am user $myname \| md5sum \| cut -d ' ' -f 1 , cat /tmp/8ca319486bfbbc3663ea0fbe81326349  |
| Level 24 | Cronjobs and bash scripting.                                                | https://mayadevbe.me/posts/overthewire/bandit/level24/                                                            |
| Level 25 | Brute-forcing with bash scripting and netcat.                               | https://mayadevbe.me/posts/overthewire/bandit/level25/                                                            |
| Level 26 | Breaking out of a restricted environment with more and vim.                 | https://mayadevbe.me/posts/overthewire/bandit/level26/                                                            |
| Level 27 | Breaking out of a restricted environment with more and vim and SUID Binary. | https://mayadevbe.me/posts/overthewire/bandit/level27/                                                            |
|          |                                                                             |                                                                                                                   |
|          |                                                                             |                                                                                                                   |
* item        Level 28 - Git introduction and basics.
* item        Level 29 - Git history.
* item        Level 30 - Git Branching Basics.
* item        Level 31 - Git Tagging.
* item        Level 32 - Git Push, Commit, Ignore, Add.
* item        Level 33 - Linux Variables and shell escape.

The Bandit wargame, found at : https://overthewire.org/wargames/bandit/

The files numbered 0,1,2 etc contains the (password) which represents the solution at each level in the game.

The command for writing the password into the files:

- echo (password)  (digit)

The command for reading these files:

- sshpass -p $(cat digit) ssh bandit(n)@bandit.labs.overthewire.org -p 2220

(password)  : The solution at each level
(digit)     : Numerical value used as file-name
(n)         : Current level in the game





| Level    | Description                                                     | Commands                                                                                             |
|----------|-----------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| 0        | SSH Login                                                       |                                                                                                      |
| Level 1  | Read a File                                                     | cat readme                                                                                           |
| Level 2  | Unusually named Files                                           | cat ./-                                                                                              |
| Level 3  | Spaces in a filename                                            | cat 'Spaces in a filename'                                                                           |
| Level 4  | Hidden Files                                                    | ls -al \| cat .hidden                                                                                |
| Level 5  | File types, specifically human-readable files.                  | for i in $(ls); do file ./$i; done    cat ./-file07                                                  |
| Level 6  | Human-readable files, file sizes and non-executable files       | find . -readable -size 1033c -not -executable ;  cat ./inhere/maybehere07/.file2                     |
| Level 7  | Find a file with specific user and group ownership              | find / -user bandit7 -group bandit6 -size 33c 2>/dev/null ;  cat /var/lib/dpkg/info/bandit7.password |
| Level 8  | Learning grep and piping                                        | cat data.txt \| grep 'millionth'                                                                     |
| Level 9  | Linux command uniq and sort, to find lines only appearing once. | cat data.txt \| sort \|uniq -c \| grep -v 10                                                         |
| Level 10 | The ‘strings’ command. Find human-readable strings in a file    | strings data.txt \| grep =                                                                           |
|          |                                                                 |                                                                                                      |
|          |                                                                 |                                                                                                      |
|          |                                                                 |                                                                                                      |


* item        Level 11 - Base64.
* item        Level 12 - Rot13 substitution cipher as Linux command with ’tr’.
* item        Level 13 - Hexdumps and compression and file signatures.
* item        Level 14 - SSH Login with key and transferring files from a remote host.
* item        Level 15 - Netcat and first network communication.
* item        Level 16 - OpenSSL, secure communication.
* item        Level 17 - Port and Service Scanning with Nmap and SSL repetition.
* item        Level 18 - Find differences in a file.
* item        Level 19 - Advanced SSH, remote command execution.
* item        Level 20 - Suid and linux permissions.
* item        Level 21 - Setuid binary, netcat and background processes/jobs.
* item        Level 22 - Cronjobs.
* item        Level 23 - Cronjobs.
* item        Level 24 - Cronjobs and bash scripting.
* item        Level 25 - Brute-forcing with bash scripting and netcat.
* item        Level 26 - Breaking out of a restricted environment with more and vim.
* item        Level 27 - Breaking out of a restricted environment with more and vim and SUID Binary.
* item        Level 28 - Git introduction and basics.
* item        Level 29 - Git history.
* item        Level 30 - Git Branching Basics.
* item        Level 31 - Git Tagging.
* item        Level 32 - Git Push, Commit, Ignore, Add.
* item        Level 33 - Linux Variables and shell escape.

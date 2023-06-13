#### This repository contains solution to the Leviathan wargame found at : https://overthewire.org/wargames/leviathan/

The Leviathan Wargame unlike the Bandit game does not require knowledge about programming. It requires a bit of common
sense and some knowledge about basic *nix commands.

**Important:** 
Data for the levels can be found in the homedirectories. You can look at /etc/leviathan_pass for the various level passwords.


The files numbered 0,1,2 etc contains the (password) which represents the solution at each level in the game.

The command for writing the password into the files:

- **echo <password) > (digit)**

The command for using these password files to ssh into the remote server:

- **sshpass -p $(cat digit) ssh leviathan(n)@leviathan.labs.overthewire.org -p 2223**


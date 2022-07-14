# Bandit Writeup

***ENDPOINT: bandit.labs.overthewire.org***
***SSHPORT: 2220***

## Level 0

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

* Username:bandit0
* Password:bandit0
 
	
## Level 0-1

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

* Username: bandit1
* Method for finding password for bandit1:
	* It was in readme file located in home directory

* Password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

## Level 1-2

The password for the next level is stored in a file called - located in the home directory

* Username: bandit2
* Method for finding password for bandit2:
	* cmd used: cat ./-
* Password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

## Level 2-3

The password for the next level is stored in a file called spaces in this filename located in the home directory

* Username: bandit3
* Method for finding password for bandit3:
	* cmd used: cat ./spaces\ in\ this\ filename

* Password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

## Level 3-4

The password for the next level is stored in a hidden file in the inhere directory.

* Username: bandit4
* Method for finding password for bandit4:
	* cmd used: cat .hidden

* Password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB

## Level 4-5

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

* Username: bandit5
* Method for finding password for bandit5:
	*cmd used: file ~/inhere/* 
* Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## Level 5-6

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable

* Username: bandiit6
* Method for finding password for bandit6:
	* cmd used: find /home/bandit5/inhere/ -type f -size 1033c

* Password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

## Level 6-7

The password for the next level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

* Username: bandiit7
* Method for finding password for bandit7:
	* cmd used: find / -user bandit7 -group bandit6 -type f -size 33c

* Password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

## Level 7-8

The password for the next level is stored in the file data.txt next to the word millionth

* Username: bandiit8
* Method for finding password for bandit8:
	* cmd used: cat data.txt | grep "millionth"

* Password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Level 8-9

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

* Username: bandit9
* Method for finding password for bandit 9:
	* cmd used: sort data.txt | uniq -c | grep "1\ "
	* Explanation: 
		* Sort the line of text in the file
		* apply uniq -c to count the no of times line of text occurs in the file
		* Using Grep to filter out count 1 

* Password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR



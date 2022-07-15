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
	* cmd used: file ~/inhere/* 
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

## Level 9-10

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

* Username: bandit10
* Method for finding password for bandit10:
	* cmd used: strings data.txt | grep "==="

* Password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

## Level 10-11

The password for the next level is stored in the file data.txt, which contains base64 encoded data

* Username: bandit11
* Method for finding password for bandit11:
	* cmd used: cat data.txt | base64 -d

* Password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR 

## Level 11-12

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

* Username: bandit12
* Method for finding password for bandit12:
	* cmd used: cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"

* Password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

## Level 12-13

The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

* Username: bandit13
* Method for finding password for bandit13:
	* cmd used:
		* xxd -r data.txt > data1
		* file data => gzip
		* mv data1 data1.gz
		* gunzip -d data1.gz 
		* file data1 => bzip2
		* mv data1 data2.bz2
		* bunzip2 -d data1.bz2 > data1
		* file data1 => gzip
		* mv data1 data1.gz
		* gunzip -d data1.gz
		* file data1 => tar archive
		* tar xvf data1 => data5.bin
		* file data5.bin => tar archive
		* tar xvf data5.bin => data6.bin
		* file data6.bin => bzip2
		* mv data6.bin data1.bz2
		* bunzip -d data2.bz2
		* file data2 => tar archive
		* tar xvf data2 => data8.bin
		* file data8.bin => gzip
		* mv data8.bin data3.gz
		* gunzip  -d data3.gz
		* file data3 => Ascii Text
		* cat data3 => Password for bandit13

* Password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL


## Level 13-14

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

* Username: bandit14
* Method for finding passowrd bandit14:
	* cmd used: cat sshkey.private 
	* Explanation:
		* The file has read only permission to bandit13 , we can read the file and copy the text and paste in to another file in our computer as id_rsa with permission 400 .

* Password:  No password for this task , we use id_rsa to login bandit14


## Level 14-15

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

* Username: bandit15
* Method for finding passowrd bandit15:
	* cmd used: 
		* cat /etc/bandit_pass/bandit14 => to get password for the current level(4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e)
		* telnet localhost 30000 => Enter current level password => password for bandit15.
	
* Password:  BfMYroe26WYalil77FoDi9qh59eK5xNr













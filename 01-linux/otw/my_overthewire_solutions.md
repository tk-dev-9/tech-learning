# Level: 0:

### Level Goal

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

### Commands Used

```
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

*for future levels must exit and ssh with new username
*new username is level number and new password is from previous level

### Password

bandit0

----------------------------------------------------------------------------------------
# Level: 1:

### Level Goal

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

### Commands Used

```
cat readme
```

### Password

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

----------------------------------------------------------------------------------------
# Level: 2:

### Level Goal

The password for the next level is stored in a file called - located in the home directory

### Commands Used

```
cat ./-
```

### Password

263JGJPfgU6LtdEvgfWU1XP5yac29mFx

### Challenges & lessons learnt

cat on its own did not work, required ./ before filename as filename is just a dash (-)
s

----------------------------------------------------------------------------------------
# Level: 3:

### Level Goal

The password for the next level is stored in a file called --spaces in this filename-- located in the home directory

### Commands Used

```
cat ./"--spaces in this filename--"
```

### Password

MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

### Challenges & lessons learnt

need ./ because of - and need "" because of spaces

----------------------------------------------------------------------------------------
# Level: 4:

### Level Goal

The password for the next level is stored in a hidden file in the inhere directory.

### Commands Used

```
cd inhere
ls -a
cat ...Hiding-From-You

```

### Password

2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

### Challenges & lessons learnt

-a after ls to see hidden files

----------------------------------------------------------------------------------------
# Level: 5:

### Level Goal

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

### Commands Used

```
cd inhere
cat ./-file07
```

### Password

4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

### Challenges & lessons learnt

Initially completed by looking in all files for readable password, trial and error, if there were a lot more files this would be time consuming

better solutions:

```
file ./*
```
outputs all file types look for one with ASCII text, then cat

OR

```
strings ./*
```
outputs all readable text from files

----------------------------------------------------------------------------------------
# Level: 6:

### Level Goal

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

### Commands Used

```
cd inhere
ls -la
cat maybehere07/.file2
```

### Password

HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

### Challenges & lessons learnt

look at all files for non executable file of size 1033 bytes, including hidden
again could take a long time if a lot of files

better solution:

```
find . -size 1033c
```

finds files of exact size 1033 bytes

----------------------------------------------------------------------------------------
# Level: 7:

### Level Goal

The password for the next level is stored somewhere on the server and has all of the following properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

### Commands Used

```
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

### Password

morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

### Challenges & lessons learnt

command searches in all directories from root for file owned by bandit7, by group bandit6 and 33 bytes

----------------------------------------------------------------------------------------
# Level: 8:

### Level Goal

The password for the next level is stored in the file data.txt next to the word millionth

### Commands Used

```
grep millionth data.txt
```

### Password

dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

### Challenges & lessons learnt

command searches through data.txt for line with millionth and prints full line including password

----------------------------------------------------------------------------------------
# Level: 9:

### Level Goal

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

### Commands Used

```
sort data.txt | uniq -u
```

### Password

4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

### Challenges & lessons learnt

"**sort**" outputs alphabetically sorted file contents

"**uniq**" outputs one of each line removing duplicates

"**uniq -u**" outputs only unique lines when comparing to its adjacent lines

using pipe symbol "**|**" to pass output (stdout) from "**sort data.txt**" as input (stdin) to uniq -u, this puts all duplicates next to each other then outputs only the unique line = password

----------------------------------------------------------------------------------------
# Level: 10:

### Level Goal

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

### Commands Used

```
strings data.txt | grep ==
```

### Password

FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

### Challenges & lessons learnt

"**strings**" outputs all readable strings from file

"**grep ==**" outputs lines with multiple =, password is there

----------------------------------------------------------------------------------------
# Level: 11:


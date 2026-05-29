# Level: 0:

## Level Goal

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

## Commands Used

'''
ssh bandit0@bandit.labs.overthewire.org -p 2220
'''

*for future levels must exit and ssh with new username
*new username is level number and new password is from previous level

## Password

bandit0

----------------------------------------------------------------------------------------
# Level: 1:

## Level Goal

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Commands Used

'''
cat readme
'''

## Password

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

----------------------------------------------------------------------------------------
# Level: 2:

## Level Goal

The password for the next level is stored in a file called - located in the home directory

## Commands Used

'''
cat ./-
'''

## Password

263JGJPfgU6LtdEvgfWU1XP5yac29mFx

# Challenges & lessons learnt

cat on its own did not work, required ./ before filename as filename is just a dash (-)
s

----------------------------------------------------------------------------------------
# Level: 3:
cat ./"--spaces in this filename--"
(need ./ because of - and need "" because of spaces)
copy password

----------------------------------------------------------------------------------------
# Level: 4:
cd inhere
ls -a
(to see hidden file)
cat ...Hiding-From-You
copy password

----------------------------------------------------------------------------------------
# Level: 5:
cd inhere
cat ./-file07
(look in all files for readable password, trial and error)
OR
file ./* (outputs file types look for one with ASCII text, then cat)
OR
strings ./* (outputs all readable text from files)
copy password


----------------------------------------------------------------------------------------
# Level: 6:
cd inhere
ls -la
(look in all files for non executable file of size 1033 bytes, could be hidden)
OR
find . -size 1033c
(faster finds exact file saves looking in each file)
cat maybehere07/.file2
copy password


----------------------------------------------------------------------------------------
# Level: 7:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
(search in all directories from root for file owned by bandit7, by group bandit6 and 33 bytes)
cat /var/lib/dpkg/info/bandit7.password
copy password

----------------------------------------------------------------------------------------
# Level: 8:
grep millionth data.txt
(will search through data.txt for line with millionth and print full line including password)
copy password

----------------------------------------------------------------------------------------
# Level: 9:
sort data.txt | uniq -u
("sort" outputs alphabetically sorted file contents)
("uniq" outputs one of each line removing duplicates)
("uniq" -u outputs only unique lines when comparing to its adjacent lines)
(using pipe symbol (|) to pass output from "sort data.txt" as input to uniq -u put all duplicates next to each other then outputs only the unique line = password)
copy password

----------------------------------------------------------------------------------------
# Level: 10:
strings data.txt | grep ==
("strings" outputs all readable strings from file)
("grep ==" outputs lines with multiple =, password is there)
copy password

----------------------------------------------------------------------------------------
# Level: 11:



# Lab Report 1 - Remote Access and FileSystem


## cd Command

#### No Args:
###### Input:
``[user@sahara ~]$ cd ``
###### Output:
``[user@sahara ~]$  ``
###### Observations:
When I first ran the command, I was in the home directory. Because I ran the cd command with no path, there was no directory to change to so I remained in the home directory.
As you can see above, the only output was the terminal command prompt in the same directory, "~", which was not in error and was the output I expected.

#### Path to a Directory:
###### Input:
``[user@sahara ~]$ cd lecture1/messages ``
###### Output:
``[user@sahara ~/lecture1/messages]$ ``
###### Observations:
The starting working directory I was in was the home directory. I then ran the cd command with the path: lecture/messages, which then changed my working directory 
to ~/lecture1/messages. The output was the terminal command prompt which reflected this change in directory. This did not produce an error and was the output that I was expecting.

#### Path to a File:
###### Input:
``[user@sahara ~/lecture1/messages]$ cd en-us.txt``
###### Output:
``bash: cd: en-us.txt: Not a directory
[user@sahara ~/lecture1/messages]$ ``
###### Observations:
The working directory I began in was ~/lecture1/messages. I then ran the cd command with the path en-us.txt which is a text file in the working directory. I then received an output that
told me that en-us.txt in the working directory ~/lecture1/messages was not a directory. It then provided the terminal prompt in the same working directory. This output was an error
as the cd command only works on directories and ~/lecture1/messages/en-us.txt is not a directory, it is a path to a file.


## ls Command

#### No Args:
###### Input:
``[user@sahara ~]$ ls ``
###### Output:
``lecture1
  [user@sahara ~]$ ``
###### Observations:
When I first ran the command, I was in the home directory. Because I ran the ls command with no path, the output I received was all of the directories found in my working directory, "~",
which would be the ~/lecture directory. This reflected in my output as the ls command output lecture1 (which was blue and embolded) and then the terminal prompt in the same working 
directory as before. This was the result I was expecting and it was not an error.

#### Path to a Directory:
###### Input:
``[user@sahara ~]$ ls lecture1/messages/ ``
###### Output:
``en-us.txt  es-mx.txt  eu.txt  zh-cn.txt
  [user@sahara ~]$ ``
###### Observations:
The starting working directory I was in was the home directory. I then ran the ls command with the path: lecture/messages/. The terminal output the files "en-us.txt  es-mx.txt  eu.txt  zh-cn.txt"
(all of which were in standard font) in addition to the terminal command prompt with the working directory "~". This did not produce an error and was the output that I was expecting.

#### Path to a File:
###### Input:
``[user@sahara ~]$ ls lecture1/messages/en-us.txt``
###### Output:
``lecture1/messages/en-us.txt
  [user@sahara ~]$ ``
###### Observations:
The working directory I began in was the home directory. I then ran the ls command with the path lecture1/messages/en-us.txt which is the path to a text file named "en-us.txt". 
I then received the output lecture1/messages/en-us.txt in addition to the terminal command prompt with the home directory. This output was not an error as the path lead to a file and ls outputs
files and directories (and their characteristics) located at the given path.


## cat Command

#### No Args:
###### Input:
``[user@sahara ~]$ cat ``
###### Output:
none
###### Observations:
The working directory I began in was the home directory. I then ran an empty cat command in this working directory. This prompted an error which left the terminal "unresponsive" and
unable to output anything. This is because the cat command must error without an absolute path. I had to use ^C to exit this loop as this error did not resolve itself.

#### Path to a Directory:
###### Input:
``[user@sahara ~]$ cat lecture1/messages/ ``
###### Output:
``cat: lecture1/messages/: Is a directory
  [user@sahara ~]$  ``
###### Observations:
The working directory I began in was the home directory. I then ran the cat command with the path lecture1/messages/ which is a path to another directory within this working directory. This
prompted the output "cat: lecture1/messages/: Is a directory". This was an error as cat only works on files and this path lead to another directory. It then closed off as usual with the 
terminal prompt in the home directory.

#### Path to a File:
###### Input:
``[user@sahara ~]$ cat lecture1/messages/en-us.txt ``
###### Output:
``Hello World!
  [user@sahara ~]$   ``
###### Observations:
I began in the working directory and used the cat command on the path lecture1/messages/en-us.txt. This path lead to a text file containing "Hello World!". The cat command output the contents
of that file, "Hello World!", as well as the terminal prompt in the same working directory, "~". This was the output was not an error and was as expected given the fact that cat prints out the
contents of the file it is given.



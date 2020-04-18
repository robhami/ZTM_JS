# ZeroToMastery- Cmd Line

How humans communicated with computers before GUI existed. 

Tend to be faster than GUI's. 

Can access servers, databases, front-end application and it can download scripts others have written from.

Installed Git to allow it to run on Windows.

#### ls command ####

Lists everything in current directory

#### pwd command ####

present work directory

#### cd ####

can go into current directory e.g. cd Desktop

#### cd .. ####

can go one directory up

#### clear ####

Clears terminal 

#### cd / #### 

Take me to root directory (i.e. every top level folder on computer)

**—> root director**

#### cd ~ ####

This takes me to user directory

#### cd <folder/folder/folder> ####

e.g. cd Desktop/test

takes to test folder on desktop. 

#### start <folder> ####

e.g. start test

will open test folder, in apple its:
open . 

that opens current folder

#### mkdir <folder> ####

e.g. mkdir test2

creates a folder

#### touch ####

e.g. touch.index.html

creates a file called index.html in the current directory

#### open application ####

1. In Git Bash copy paste and run:
echo 'alias subl="/C/Program\ Files/Sublime\ Text\ 3/sublime_text.exe"' >> ~/.bashrc
2. Close Git Bash and Open it again.
3. In Git bash type:
subl

open file in application: 

subl index.html

#### mv ####

e.g mv index.html about.html

rename file, its actually move commend but work to rename file. 


#### rm ####

e.g. rm.about.html

removes file

to remove folder can use rm-r

e.g. rm -r test2


** <> means to add your own folder names that exist on your computer.
mkdir <folder>
open <folder> **for windows use: start <folder>
touch index.html  **for windows use: echo "" > index.html
open index.html **for windows use: start index.html
open -a “Sublime Text”  **for windows see the note about this at the bottom of this lecture!!
open . **for windows use: start .
mv index.html about.html
*Try using the Up and Down arrow.
 
rm <file>
rm -r <folder>
say hello **(only on Mac)**

Quick Note: For Windows Users
In the next video, please ignore the text at the bottom. Instead, you will find all of the equivalent Windows commands below. The text at the bottom of the next lecture is for another option for Windows users which is Command Prompt which I do not recommend for this course (I left the text in the video for reference only):
Windows ONLY: How to open -a “Sublime Text”  in windows?

**Assuming your Sublime Text 3 was located in the "C:\Program Files\Sublime Text 3" directory**

1. In Git Bash copy paste and run:
echo 'alias subl="/C/Program\ Files/Sublime\ Text\ 3/sublime_text.exe"' >> ~/.bashrc



2. Close Git Bash and Open it again.



3. In Git bash type:

subl


# UNIX_commands
Some commonly used UNIX commands.


Unix commands – 
ls -al 					                          Lists all files including hidden files.
ls -R dir				                          Lists recursively all directories and subdirectories in dir
ls -lar > ls-lar	                        Lists recursively all directories and subdirectories and stores them in a file ls-lar

mkdir dire				                        Creates a new directory dire
mkdir -p dir1/dir2/dir3	                  Creates multiple new directories & parent directory if they don’t exist

cp <options> file1 file2…dest_dir	        copies one or more files to a destination directory
cp a.txt dir1		                          copies file a.txt into dir1
cp a.txt b.txt		                        creates a copy of a.txt called b.txt
cp -R dir1 dir2	                          copy recursively directories and subdirectories of dir1 into dir2

mv file1 dest_dir	                        moves file1 to dest_dir
mx a.txt b.txt	                          renames a.txt to b.txt

rm <options> file1 file2	                removes a list of files
rm -f a.txt	                              Removes a.txt and do not send error message if it fails.
rm -R dir1	                              Removes dir1 and all its contents

grep <options> pattern file1 file2	      Print lines that contain “patter” in the files
grep hello a.txt	                        Print lines from a.txt wherever there is “hello”
grep hello * */* */*/*	                  Print lines that contain hello in any file in the directory and subdirectories.

NOTE – we get errors while using this, because we are using it in a directory. 
To get rid of the errors, we redirect stderr. We do using the following command –
grep hello * */* */*/* 2> err.txt	        Will put all errors in the file err.txt

If we don’t want to generate any errors at all we use – 
grep hello * */* */*/* 2> /dev/null       /dev/null	It is like a blackhole, we push in there everything we don’t want.

echo *	                                  Print all files in directory
echo */*	                                Print all files under first level directory

man <options> command	                    Prints manual pages for that command
man cp	                                  Prints manual pages related to cp
man -k pthread	                          Prints all manual pages that contain string “pthread”
man -s 3 exec	                            Print manual pages of exec from section 3
  
NOTE – man pages are divided into sections as follows – 
Section1 – UNIX commands (cp, mv etc)
Section2 – system calls (fork)
Section3 – C standard library

whereis 				                          Prints where all the thing is
whereis python			                      Prints all paths of files where python is located
NOTE – It works only if the OS created a database with files in the file system.

which 				                            Prints the path of the command that will be executed by shell if “command” is typed
which python				                      Prints the path of the python that will be used by the shell.

head file				                          lists first 10 lines of the file
head -5 file				                      lists first 5 lines of the file

tail file			                           	lists last 10 lines of the file
tail -15 file				                      lists last 15 lines of the file
tail -f a.log				                      it will periodically print the lines of a.log as they are added

awk (pattern scanning and processing language)
We can use awk for simple text manipulation:
Example:
awk ‘{print $1;}’ m.txt			               print first word in each line in m.txt
tail -10 m.txt | awk ‘{print $1;}’.        print first word for only last 10 lines in m.txt, as output from first is used as input for second using pipe. 

sed (simple line editor, or text processing)
sed s/current/new/g hello.sh > hello2.sh

“s” – substitute “current” with “new”
“g” – do it globally
Input file “hello.sh”, and output file will be “hello2.sh”

find (recursively descends the directory hierarchy for each path seeking files that match a Boolean expression)
find . -name “*.conf” -print		                find recursively all files with “.conf” extension
find . -name “*.conf” -exec chmod o+r ‘{}’ \;	  find recursively and make readable by others all files with “.conf” extension

chmod 775 ./script1.sh                          To change permissions of a file (in case they are only readable and writable but not executable):




0-Write a script that prints “Hello, World”, followed by a new line to the standard output.
Ans:  echo "HELLO,World"

1-Write a script that displays a confused smiley "(Ôo)'.
Ans: echo "\"(Ôo)'"

2-Display the content of the /etc/passwd file.
Ans: cat /etc/passwd

3-Display the content of /etc/passwd and /etc/hosts
Ans: cat /etc/passwd /etc/hosts

4- Display the last 10 lines of /etc/passwd
Ans: tail /etc/passwd

5-Display the first 10 lines of /etc/passwd 
Ans:  head /etc/passwd

6- Write a script that displays the third line of the file iacta. 
Ans: head -3 iacta | tail -1

7- Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.
Ans: echo "Best School" >> '\\\'\''"Best School"\'\''\\$\?\\\\\*:)'

8-Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.
Ans: ls -la > ls_cwd_content

9- Write a script that duplicates the last line of the file iacta
Ans: tail -1 < iacta >> iacta

10- Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders. 
Ans: find -name "*.js" -type f -delete

11- Write a script that counts the number of directories and sub-directories in the current directory.

    The current and parent directories should not be taken into account
    Hidden directories should be counted
Ans: find . -type d ! -path . -print | wc -l

12- Create a script that displays the 10 newest files in the current directory.

Requirements:

    One file per line
    Sorted from the newest to the oldest
 
Ans: ls -1t | head -10

13- Create a script that takes a list of words as input and prints only words that appear exactly once.

    Input format: One line, one word
    Output format: One line, one word
    Words should be sorted

Ans: sort | uniq -u

14- Display lines containing the pattern “root” from the file /etc/passwd
Ans:  grep "root" /etc/passwd

15- Display the number of lines that contain the pattern “bin” in the file /etc/passwd
Ans: grep -c "bin" /etc/passwd

16- Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.
Ans: grep -A 3 "root" /etc/passwd

17-Display all the lines in the file /etc/passwd that do not contain the pattern “bin”. 
Ans: grep -v "bin" /etc/passwd

18-Display all lines of the file /etc/ssh/sshd_config starting with a letter.
Ans: grep ^[[:alpha:]] /etc/ssh/sshd_config

19-Replace all characters A and c from input to Z and e respectively.
Ans: tr 'A' 'Z' | tr 'c' 'e'

20- Create a script that removes all letters c and C from input.
Ans: tr -d 'c' | tr -d 'C'

21- Write a script that reverse its input. 
Ans: rev

22- Write a script that displays all users and their home directories, sorted by users.

    Based on the the /etc/passwd file
 
Ans: cut -d':' -f1,6 /etc/passwd | sort

23-Write a command that finds all empty files and directories in the current directory and all sub-directories.

    Only the names of the files and directories should be displayed (not the entire path)
    Hidden files should be listed
    One file name per line
    The listing should end with a new line
    You are not allowed to use basename, grep, egrep, fgrep or rgrep

Ans: find . -empty -printf "%f\n"

24-Write a script that lists all the files with a .gif extension in the current directory and all its sub-directories.

    Hidden files should be listed
    Only regular files (not directories) should be listed
    The names of the files should be displayed without their extensions
    The files should be sorted by byte values, but case-insensitive (file aaa should be listed before file bbb, file .b should be listed before file a, and file Rona should be listed after file jay)
    One file name per line
    The listing should end with a new line
    You are not allowed to use basename, grep, egrep, fgrep or rgrep

Ans: find -type f -name "*.gif" | rev | cut -d "/" -f 1 | cut -d '.' -f 2- | rev | LC_ALL=C sort -f

25- An acrostic is a poem (or other form of writing) in which the first letter (or syllable, or word) of each line (or paragraph, or other recurring feature in the text) spells out a word, message or the alphabet. The word comes from the French acrostiche from post-classical Latin acrostichis). As a form of constrained writing, an acrostic can be used as a mnemonic device to aid memory retrieval. Read more.

Create a script that decodes acrostics that use the first letter of each line.

    The ‘decoded’ message has to end with a new line
    You are not allowed to use grep, egrep, fgrep or rgrep

Ans: cut -c 1 | tr -d '\n' | sort

26-Write a script that parses web servers logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests.

    Order by number of requests, most active host or IP at the top
    You are not allowed to use grep, egrep, fgrep or rgrep
 
Ans: tail -n +2 | cut -f1 | sort | uniq -c | sort -nr -k 1,1 | cut -c 9- | head -11

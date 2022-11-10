SIMPLE SHELL
Tasks

0. Betty would be proud

mandatory

Write a beautiful code that passes the Betty checks



Repo:



GitHub repository: simple_shell

  

1. Simple shell 0.1

mandatory

Write a UNIX command line interpreter.



Usage: simple_shell

Your Shell should:



Display a prompt and wait for the user to type a command. A command line always ends with a new line.

The prompt is displayed again each time a command has been executed.

The command lines are simple, no semicolons, no pipes, no redirections or any other advanced features.

The command lines are made only of one word. No arguments will be passed to programs.

If an executable cannot be found, print an error message and display the prompt again.

Handle errors.

You have to handle the “end of file” condition (Ctrl+D)

You don’t have to:



use the PATH

implement built-ins

handle special characters : ", ', `, \, *, &, #

be able to move the cursor

handle commands with arguments

execve will be the core part of your Shell, don’t forget to pass the environ to it…



julien@ubuntu:~/shell$ ./shell 

#cisfun$ ls

./shell: No such file or directory

#cisfun$ /bin/ls

barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell.c  stat.c         wait

env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     stat test_scripting.sh  wait.c

#cisfun$ /bin/ls -l

./shell: No such file or directory

#cisfun$ ^[[D^[[D^[[D

./shell: No such file or directory

#cisfun$ ^[[C^[[C^[[C^[[C

./shell: No such file or directory

#cisfun$ exit

./shell: No such file or directory

#cisfun$ ^C

julien@ubuntu:~/shell$ echo "/bin/ls" | ./shell

barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell.c  stat.c         wait

env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     stat test_scripting.sh  wait.c

#cisfun$ julien@ubuntu:~/shell$

Repo:



GitHub repository: simple_shell

  

2. Simple shell 0.2

mandatory

Simple shell 0.1 +



Handle command lines with arguments

Repo:



GitHub repository: simple_shell

  

3. Simple shell 0.3

mandatory

Simple shell 0.2 +



Handle the PATH

fork must not be called if the command doesn’t exist

julien@ubuntu:~/shell$ ./shell_0.3

:) /bin/ls

barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell_0.3  stat    test_scripting.sh  wait.c

env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     shell.c    stat.c  wait

:) ls

barbie_j       env-main.c  exec.c  fork.c  pid.c  ppid.c    prompt   prompt.c  shell_0.3  stat    test_scripting.sh  wait.c

env-environ.c  exec    fork    mypid   ppid   printenv  promptc  shell     shell.c    stat.c  wait

:) ls -l /tmp 

total 20

-rw------- 1 julien julien    0 Dec  5 12:09 config-err-aAMZrR

drwx------ 3 root   root   4096 Dec  5 12:09 systemd-private-062a0eca7f2a44349733e78cb4abdff4-colord.service-V7DUzr

drwx------ 3 root   root   4096 Dec  5 12:09 systemd-private-062a0eca7f2a44349733e78cb4abdff4-rtkit-daemon.service-ANGvoV

drwx------ 3 root   root   4096 Dec  5 12:07 systemd-private-062a0eca7f2a44349733e78cb4abdff4-systemd-timesyncd.service-CdXUtH

-rw-rw-r-- 1 julien julien    0 Dec  5 12:09 unity_support_test.0

:) ^C

julien@ubuntu:~/shell$ 

Repo:



GitHub repository: simple_shell

  

4. Simple shell 0.4

mandatory

Simple shell 0.3 +



Implement the exit built-in, that exits the shell

Usage: exit

You don’t have to handle any argument to the built-in exit

Repo:



GitHub repository: simple_shell

  

5. Simple shell 1.0

mandatory

Simple shell 0.4 +



Implement the env built-in, that prints the current environment

julien@ubuntu:~/shell$ ./simple_shell

$ env

USER=julien

LANGUAGE=en_US

SESSION=ubuntu

COMPIZ_CONFIG_PROFILE=ubuntu

SHLVL=1

HOME=/home/julien

C_IS=Fun_:)

DESKTOP_SESSION=ubuntu

LOGNAME=julien

TERM=xterm-256color

PATH=/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

DISPLAY=:0

$ exit

julien@ubuntu:~/shell$ 

Repo:



GitHub repository: simple_shell

  

6. Simple shell 0.1.1

#advanced

Simple shell 0.1 +



Write your own getline function

Use a buffer to read many chars at once and call the least possible the read system call

You will need to use static variables

You are not allowed to use getline

You don’t have to:



be able to move the cursor

Repo:



GitHub repository: simple_shell

  

7. Simple shell 0.2.1

#advanced

Simple shell 0.2 +



You are not allowed to use strtok

Repo:



GitHub repository: simple_shell

  

8. Simple shell 0.4.1

#advanced

Simple shell 0.4 +



handle arguments for the built-in exit

Usage: exit status, where status is an integer used to exit the shell

julien@ubuntu:~/shell$ ./shell_0.4.1

$ exit 98

julien@ubuntu:~/shell$ echo $?

98

julien@ubuntu:~/shell$ 

Repo:



GitHub repository: simple_shell

  

9. setenv, unsetenv

#advanced

Simple shell 1.0 +



Implement the setenv and unsetenv builtin commands



setenv

Initialize a new environment variable, or modify an existing one

Command syntax: setenv VARIABLE VALUE

Should print something on stderr on failure

unsetenv

Remove an environment variable

Command syntax: unsetenv VARIABLE

Should print something on stderr on failure

Repo:



GitHub repository: simple_shell

  

10. cd

#advanced

Simple shell 1.0 +



Implement the builtin command cd:



Changes the current directory of the process.

Command syntax: cd [DIRECTORY]

If no argument is given to cd the command must be interpreted like cd $HOME

You have to handle the command cd -

You have to update the environment variable PWD when you change directory

man chdir, man getcwd



Repo:



GitHub repository: simple_shell

  

11. ;

#advanced

Simple shell 1.0 +



Handle the commands separator ;

alex@~$ ls /var ; ls /var

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$ ls /hbtn ; ls /var

ls: cannot access /hbtn: No such file or directory

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$ ls /var ; ls /hbtn

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

ls: cannot access /hbtn: No such file or directory

alex@~$ ls /var ; ls /hbtn ; ls /var ; ls /var

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

ls: cannot access /hbtn: No such file or directory

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$

Repo:



GitHub repository: simple_shell

  

12. && and ||

#advanced

Simple shell 1.0 +



Handle the && and || shell logical operators

alex@~$ ls /var && ls /var

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$ ls /hbtn && ls /var

ls: cannot access /hbtn: No such file or directory

alex@~$ ls /var && ls /var && ls /var && ls /hbtn

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

ls: cannot access /hbtn: No such file or directory

alex@~$ ls /var && ls /var && ls /var && ls /hbtn && ls /hbtn

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

ls: cannot access /hbtn: No such file or directory

alex@~$

alex@~$ ls /var || ls /var

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$ ls /hbtn || ls /var

ls: cannot access /hbtn: No such file or directory

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$ ls /hbtn || ls /hbtn || ls /hbtn || ls /var

ls: cannot access /hbtn: No such file or directory

ls: cannot access /hbtn: No such file or directory

ls: cannot access /hbtn: No such file or directory

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$ ls /hbtn || ls /hbtn || ls /hbtn || ls /var || ls /var

ls: cannot access /hbtn: No such file or directory

ls: cannot access /hbtn: No such file or directory

ls: cannot access /hbtn: No such file or directory

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  spool  tmp

alex@~$

Repo:



GitHub repository: simple_shell

  

13. alias

#advanced

Simple shell 1.0 +



Implement the alias builtin command

Usage: alias [name[='value'] ...]

alias: Prints a list of all aliases, one per line, in the form name='value'

alias name [name2 ...]: Prints the aliases name, name2, etc 1 per line, in the form name='value'

alias name='value' [...]: Defines an alias for each name whose value is given. If name is already an alias, replaces its value with value

Repo:



GitHub repository: simple_shell

  

14. Variables

#advanced

Simple shell 1.0 +



Handle variables replacement

Handle the $? variable

Handle the $$ variable

julien@ubuntu:~/shell$ ./hsh

$ ls /var

backups  cache  crash  lib  local  lock  log  mail  metrics  opt  run  snap  spool  tmp

$ echo $?

0

$ echo $$

5104

$ echo $PATH

/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

$ exit 

julien@ubuntu:~/shell$ 

Repo:



GitHub repository: simple_shell

  

15. Comments

#advanced

Simple shell 1.0 +



Handle comments (#)

julien@ubuntu:~/shell$ sh

$ echo $$ # ls -la

5114

$ exit

julien@ubuntu:~/shell$ 

Repo:



GitHub repository: simple_shell

  

16. File as input

#advanced

Simple shell 1.0 +



Usage: simple_shell [filename]

Your shell can take a file as a command line argument

The file contains all the commands that your shell should run before exiting

The file should contain one command per line

In this mode, the shell should not print a prompt and should not read from stdin

Repo:



GitHub repository: simple_shell
Collaboration between Jackson Arrey And Uwem Dickson

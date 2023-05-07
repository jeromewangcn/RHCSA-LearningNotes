# Basic System Management Tasks
## Using the command line
Shell is the environment where the user interfaces with the operating system<br>
Bash is the default command line shell<br>
Use `who` or `w` command to see which users currently are active on which terminals
```
[jerome@DESKTOP-6UCNNF9 RHCSA-LearningNotes]$ w
 23:22:02 up  2:32,  0 users,  load average: 0.00, 0.00, 0.00
USER     TTY        LOGIN@   IDLE   JCPU   PCPU WHAT
```
Use `chvt` to change between virtual terminals<br>
## Exploring essential tools
Use `man` command to check the usage of one commmand
```
[jerome@JeromePC RHCSA-LearningNotes]$ man pacman
PACMAN(8)                                                                                  Pacman Manual                                                                                  PACMAN(8)

NAME
       pacman - package manager utility

SYNOPSIS
       pacman <operation> [options] [targets]

DESCRIPTION
       Pacman is a package management utility that tracks installed packages on a Linux system. It features dependency support, package groups, install and uninstall scripts, and the ability to
       sync your local machine with a remote repository to automatically upgrade packages. Pacman packages are a zipped tar format.
```
Use `/` in man page to search the keyword you want<br>
Documentation in `man` is orgnanized in many different sections:<br>
1 Executable programs or shell commands, like `mkdir`<br>
5 File formats and conventions<br>
8 System administration commands, like `pacman`<br>

All `man` pages are indexed in the manddb. Use `man -k` or `apropos` to search the mandb based on the keyword. And you and use `grep` to filter the results. For example, if you want to findout how to create a user, and this is a administrator task use the command below
```
[jerome@JeromePC RHCSA-LearningNotes]$ man -k user | grep 8
applygnupgdefaults (8) - Run gpgconf --apply-defaults for all users.
arpd (8)             - userspace arp daemon.
groupmems (8)        - administer members of a user's primary group
```
Linux comman editor could be `nano` and `vim` <br>
`Vim` has different modes:<br>
- Command mode, which is dafault after opening, press `esc` to enter command mode
- Insert mode, where you can enter text, press `i` to enter insert mode<br>

Some command need to be remembered:
- `Esc`   Enter command mode
- `i,a`   Enter input mode
- `:wq`   Write and quit
- `:q!`   Quit witout saving anything
- `dd`    Delete current line
- `yy`    Copy current line
- `p`     Paste the text in the buffer
- `v`     Enter visual mode
- `u`     Undo the previous
- `r`     Redo the previous
- `gg`    Go to the top
- `G`     Go to the end
- `/text` Search for "text"
- `?text` Search backwards for "text'
- `^`     Move to start of line
- `$`     Move to end of the line
- `w`     Move to the next word
- `%s/old/new/g` Substitute all occurrences of "old" with "new"

1. Locate the man page that shows how to set a password
```
[jerome@JeromePC RHCSA-LearningNotes]$ man -k password
passwd (1)           - change user password
passwd (5)           - the password file
[jerome@JeromePC RHCSA-LearningNotes]$ man passwd
PASSWD(1)                                                                                  User Commands                                                                                  PASSWD(1)

NAME
       passwd - change user password

SYNOPSIS
       passwd [options] [LOGIN]

DESCRIPTION
       The passwd command changes passwords for user accounts. A normal user may only change the password for their own account, while the superuser may change the password for any account.
       passwd also changes the account or associated password validity period.
```
2. Create a user with with the name anna
```
[jerome@JeromePC RHCSA-LearningNotes]$ sudo useradd anna
[sudo] password for jerome:
```
3. Set the password for anna to "password"
```
[jerome@JeromePC RHCSA-LearningNotes]$ sudo passwd anna
New password: 
Retype new password: 
passwd: password updated successfully
```
4. Use the vim to create a file with the name users, contain the name alex, alexander, linda, and belinda on separate lines
```
[jerome@JeromePC RHCSA-LearningNotes]$ cat users

alex
alexandar
lind
belinda
```







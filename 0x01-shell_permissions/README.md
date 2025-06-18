# Shell Permission

The Unix-like operating sytems, such as linux differ from other computing systems in that they are not only multitasking but also multi-user.

What does this actually means? It means that more than one user can operating the computer at the same time.
While a desktop or laptop computer only has one keyboard and monitor, It can still be used by more than one user.
For example, if the computer is attached to a network, or the Internet, remote users can execute graphical applications and have the output displayed on a remote computer.

In order to make this practical, a method had to be devised to protect the users from each other. After all, we wouldn't want the actions of one user to crash the computer, nor would we allow one user to interfere with the files belonging to another user.

This lesson will cover the following commands:

- chmod - modify file access rights
- SU - temporarily become the superuser
- CHOWN - change file ownership
- CHGRP - change a file's group ownership

## chmod

The chmod command is used to change the permissions of a file or directory. To use it, we specify the desired permission settings and the file or files that we wish to modify. There are two ways to specify the permissions. In this lesson we will focus on one of these, called the octal notation method.

It is easy to think of the permission settings as a series of bits (which is how the computer thinks about them). Here's how it works:

- rwx rwx twx = 111 111 111
- rw- rw- rw- = 110 110 110

and so on.....

- rwx = 111 in binary = 7
- rw- = 110 in binary = 6
- r-x = 101 in binary = 5
- r-- = 100 in binary = 4

Now, if we represent each of the three sets of permissions (owner, group, and other) as a single digit, we have a pretty convenient way of expressing the possible permissions settings. For example, if we wanted to set some_file to have read and write permission for the owner, but want to keep the file private from others, we would:

[me@linuxbox me]$ chmod 600 some_file

Here is a table of numbers that covers all the common settings. The ones beginning with "7" are used with programs (since they enables execution) and the rest are for other kinds of files.

| Value | Meaning                                                                                                                        |
| ----- | ------------------------------------------------------------------------------------------------------------------------------ |
| 777   | (rwxrwxrwx) No restrictions on permissions. Anybody may do anything. Generally not a desirable setting.                        |
| 755   | (rwxr-xr-x) The file's owner may read, write and execute the file. The setting common for programs that are used by all users. |

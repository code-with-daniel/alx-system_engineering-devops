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

| Value | Symbolic  | Meaning                                                                                             |
| ----- | --------- | --------------------------------------------------------------------------------------------------- |
| 777   | rwxrwxrwx | No restrictions. Anybody may read, write, and execute. **Not recommended** due to security risks.   |
| 755   | rwxr-xr-x | Owner may read/write/execute. Others may read and execute. Common for shared programs.              |
| 700   | rwx------ | Only the owner may read/write/execute. Useful for private scripts and executables.                  |
| 666   | rw-rw-rw- | All users may read and write. **Execute permission is not granted**.                                |
| 644   | rw-r--r-- | The owner may read and write a file while all others may only read the file.                        |
| 600   | rw------- | The owner may read and write a file. All others have no rights. A common settings for owner privacy |

## Directory Permissions

The `chmod` command can also be used to control the access permissions for directories. Again, we can use the octal notation to set permissions, but the meaning of the r, w, and x attributes is different:

- r - Allows the contents of the directory to be listed if thr x attributes is also set.
- w - Allows files within the directory to be created, deleted, or renamed if the `x` attribute is also set.
- x - Allows a directory to be entered (i.e cd dir).

## Becoming the Superuser for a short while

It is often necessary to become the superuser to perform important system administration tasks, but as we know we should not stay logged in as the superuser. In most distributions, there is a program that can give you temporary access to the superuser's privileges. This program is called `su` (short for substitute user) and can be used in those cases when you need to be the superuser for a small number of tasks. To become the superuser, simply type the `su` command. you will be prompted for the superuser's password.

After executing the `su` command, we have a new shell session as the superuser. To exit the superuser session, type `exit` and we will return to your previous session.

## Changing File Ownership

We can change the owner of a file by using the `chown` Hers's an exampleL: Suppose we wanted to change the owner of some_file from "me" to "you" we could: [me@linuxbox me]$ sudo chown you some_file

Notice that in order to change the owner of a file, we must have the superuser privileges. To do this, our example employed the `sudo` command to execute the `chown`
`chown` works the same way on directories as it does on files.

## Changing Group Ownership

The group ownership of a file or directory may be changed with `chgrp` This command is used like this:
[me@linuxbox me]$ chgrp new_group some_file

In the example above, we changed the group ownership of some_file from its previous group to "new_group". We must be the owner of the file or directory to perform a `chgrp`.

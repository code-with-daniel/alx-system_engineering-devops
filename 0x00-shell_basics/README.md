# Shell Basics

The shell is a program that takes command from the keybaord and give them to the operating system to perform.
so in the old days it was the only user interface available on a unix like system, nowadays we have Graphical User Interface (GUI) in addtion to command line interface (CLI) such as "The Shell".

## What's a Terminal ?

A terminal is a program that lets you interact with the shell. There are bunch of different terminal emulators we can use. These might include gnome-terminal, konsole, xterm, rxvt, kvt, nxterm, and eterm.

## Shell Prompt

When you open up a terminal the first thing you see is a shell prompt that contains our user name and the name of the machine followed by a dollar sign.

## Navigation

Navigation typically refers to as moving around in a command-line interface (CLI).
So we going to look at few commands and what they do.

- cd -> change working directory
- pwd -> prints working directory
- ls -> list files and directory
- clear -> clears the terminal screen
- ls -a -> shows hiddens files
- ls -l -> long listing format with permissions,size,etc
- cd .. -> go to parent directory/moves up one level
  and many more

## Looking Around

- less — View the contents of a file one screen at a time
- file describe what type of file it is

## Using Options and Arguments with Commands

Options modify how a command behaves (eg: -l for long format)
Argument are the targets (eg: which files/folder to act on)

Example: ls -l /etc # Option: -l, Argument: /etc directory

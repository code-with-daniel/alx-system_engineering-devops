# I/O Redirection

In this lesson, we will explore a powerful feature used by command line programs called input/output redirection. As we have seen, many commands such as `ls` print thier output on the display. This does not have to be the case, however. By using some special notations we can redirect the output of many commands to files, devices, and even to the input of other commands.

## Standard Output

Most command line programs that displays thier result do so by sending thier results to facility called `standard output`. By default, standard output directs its contents to the display. To redirect standard output to a file, the ">" character is used like this below:

- [me@linuxbox me]$ ls > file_list.txt
  In the example above the `ls` command is executed and the results are written in a file named file_list.txt. Since the output of `ls` was redirected to the file, no result will appear on the display. Each time the command above is repeated, file_list.txt is overwritten from the beginning with the output of the command `ls`. To have the new results appended to the file instead, we use ">>" like this:
- [me@linuxbox me]$ls >> file_list.txt

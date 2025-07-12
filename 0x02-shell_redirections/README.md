# I/O Redirection

In this lesson, we will explore a powerful feature used by command line programs called input/output redirection. As we have seen, many commands such as **ls** print thier output on the display. This does not have to be the case, however. By using some special notations we can redirect the output of many commands to files, devices, and even to the input of other commands.

## Standard Output

Most command line programs that displays thier result do so by sending thier results to facility called `standard output`. By default, standard output directs its contents to the display. To redirect standard output to a file, the ">" character is used like this below:

- **[me@linuxbox me]$ ls > file_list.txt**
  In the example above the **ls** command is executed and the results are written in a file named file_list.txt. Since the output of **ls** was redirected to the file, no result will appear on the display. Each time the command above is repeated, file_list.txt is overwritten from the beginning with the output of the command **ls**. To have the new results appended to the file instead, we use ">>" like this:
- **[me@linuxbox me]$ls >> file_list.txt**
  When the results are appended, the new results are added to the end of the file, thus making the file longer each time the command is repeated. if the file does not exist when we attempt to append the redirection output, the file will be created.

## Standard Input

Many commands can accept inputs from a facility called **standard input.** By default, standard input gets its contents from the keyboard, but like standard output, it can be redirected. To redirect standard input from a file instead of the keyboard, the "<" character is used like this:

- **[me@linuxbox me]$ sort < file_list.txt**

In the example above, we used **sort** command to process the contents of \*\*file_list.txt The result are output on the display since the standard output was not redirected. We could redirect standard output to another file like this: **[me@linuxbox me]$ sort < file_list.txt > sorted_file_list.txt**
As we can see, a command can have both its input and output redirected. Be aware that the order of the redirection does not matter. The only requirement is that the redirection operators (the "< abd >") must appear after the other options and arguments in the command.

## Pipelines

The most useful and powerful thing we can do with I/O redirection is to connect multiple commands together to form what are called pipelines. With piplines, the standard output of one command is fed in the standard input of another. Here is a ver useful example:

### [me@linuxbox me]$ ls -l | less

In this example, the output of the **ls** command is fed in the less. By using this **"| less"** trick, we can make any command have the scrolling output.

By conecting commands together, we can accomplish amazing feats. Here are some examples to try

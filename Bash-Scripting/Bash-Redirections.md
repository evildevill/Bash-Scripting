# Bash redirections

# Standard file descriptors

| File Descriptor | Abbreviation | Description |
| --- | --- | --- |
| 0 | STDIN | Standard input, The input is read from what you type in the terminal using your keyboard. When you use the input redirect symbol (<), Linux substitutes the file referenced by the redirection for the standard input file descriptor. It reads the file and retrieves data in the same way that you would type it on a keyboard. |
| 1 | STDOUT | Standard Output. The terminal monitor is the standard output on a terminal interface. All output from the shell (including programs and scripts run in the shell) is directed to the monitor's standard output. When you use the output redirect symbol (>), Linux replaces the terminal with a file referenced by the redirection symbol. |
| 2 | STDERR | Standard Error. The STDERR file descriptor, by default, points to the same location as the STDOUT file descriptor (despite being assigned different file descriptor values). This means that by default, all error messages are displayed on the monitor. To  redirect the errors you use a special redirection operator 2> . |

<aside>
💡 Unless they are closed, file descriptors always point to a file. When bash starts, all three file descriptors, stdin (file descriptor 0), stdout (file descriptor 1), and stderr (file descriptor 2), usually point to your terminal.

You can also open and close additional file descriptors (such as 3, 4, 5,...). File descriptors can also be copied. You can also write to and read from them.

</aside>

# Redirections Operators

| Redirection | Description |
| --- | --- |
| command > file | Redirect the standard output (stdout) of a command to a specified file. This also the same as command 1> file , as 1 is the default file descriptor (fd) for standard output (stdout). |
| command 2> file | Redirect the standard error (stderr) of a command to a specified file. 2 is the default file descriptor (fd) for standard error (stderr). |
| command >> file | Redirect the standard output (stdout) of a command to a specified file without overriding the existing data. |
| command 2>> file | Redirect the standard error (stderrt) of a command to a specified file without overriding the existing data. |
| command &> file | Redirect both the standard output (stdout) and  standard error (stderr) of a command to a file. This is also the same as command > file 2>&1  but command 2>&1 > file  (the redirection order matters!) |
| command > /dev/null | Discard  standard output (stdout) of a command. The  /dev/null  is  a special file that discards all data written to it. |
| command 2> /dev/null | Discard  standard error (stderr) of a command.  |
| command &> /dev/null | Discard  both the  standard output (stdout) and the standard error (stderr) of a command. This also the same as command >/dev/null 2>&1. |
| command < file | Redirect the contents of the file to the standard input (stdin) of a command. This also the same as command 0< file . 0 is the default file descriptor (fd) for standard input (stdin). |
| command << EOL
line1
line2
EOL | Redirect a bunch of lines to the standard input (stdin) of a command using the here-document redirection operator <<MARKER . This operator instructs bash to read the input from stdin until a line containing only MARKER
 is found. |
| command <<- EOL
<tab>foo
<tab><tab>bar
EOL | Redirect a bunch of lines to the standard input (stdin) and strip the all leading tabs. Notice the difference (<<- ) |
| command <<< 'string'
command <<< $word | The here string is used for input redirection from a single line of text or a variable. A here string can be considered as a stripped-down form of here document |
| command >| file | Overrides the noclobber shell option ( Bash options (Bash%20options%2017ca5e7d4e24479cac437bcb80c203a7.md))  |
| exec 2> file | Redirect standard error of all commands to a file forever. |
| exec > file | Redirect standard output of all commands to a file forever. |
| exec 3< file | Create a custom file descriptor (3) for reading from a file |
| exec 3> file | Create a custom file descriptor (3) for writing to a file |
| exec 3<> file | Create a custom file descriptor (3) for both writing and reading a file |
| exec 3>&- | Close the created file descriptor. |
| exec 4<&3 | Make file descriptor 4 to be a copy of file descriptor 3. (Copy fd 3 to 4.) |
| exec 4>&3- | Copy file descriptor 3 to 4 and close file descriptor 3. |
| echo "foo" >&3 | Write to a custom file descriptor 3. |
| cat <&3 | Read from a custom file descriptor 3. |
| exec 3<> /dev/tcp/host/port | Open a TCP connection to host:port. (This is a bash feature, not Linux feature). |
| exec 3<> /dev/udp/host/port | Open a UDP connection to host:port. (This is a bash feature, not Linux feature). |
| (command1; command2) > file | Redirect stdout from multiple commands to a file (using a sub-shell). The parenthesis instructs bash to create a subshell and run commands from there. |
| { command1; command2 } > file | Redirect stdout from multiple commands to a file (This is faster as there is no need setting up a subshell environment to execute the commands). Notice the trailing and leading spaces between the curly braces and the commands. |
| command <(command1) | Redirect stdout of command1 to an anonymous  pipe fifo, then pass the fifo to command as an argument. Useful when command doesn’t read from stdin directly. |
| command < < (command1) | Redirect stdout of command to an anonymous pipe fifo, then redirect the fifo to stdin of command. Best example: diff <(find /path1 | sort) <(find /path2 | sort). |
| command <(command1) <(command2) | Redirect stdout of command1 and command2 to two anonymous fifos, then pass both fifos as arguments to command. |
| command1 >(command2) | Run command2 with its stdin connected to an anonymous fifo, and pass the filename of the pipe as an argument to command1. |
| command1 > > (command2) | Run command2 with its stdin connected to an anonymous fifo, then redirect stdout of command1 to this anonymous pipe. |
| command1 | command2 | Redirect stdout of command1 to stdin of command2. Pro-tip: This is the same as command1`> >` (command2), same as cmd2 < <(cmd1), same as > >(cmd2) cmd1, same as < <(cmd1) cmd2. |
| command1 |& command2 | Redirect stdout and stderr of command1 to stdin of command2 (bash 4.0+ only). Use command2>&1 | command2 for older bashes. |
| commnad | tee file | Redirect stdout of commmand to a file and print it to screen. |
| exec {filew}> file | Open a file for writing using a named file descriptor called {filew} (bash 4.1+). |
| command 3>&1 1>&2 2>&3 | Swap stdout and stderr of command . |
| cmd > >(cmd1) 2> >(cmd2) | Send stdout of cmd to cmd1 and stderr of cmd to cmd2. |
| cmd1 | cmd2 | cmd3 | cmd4
echo ${PIPESTATUS[@]} | Find out the exit codes of all piped commands. |

<aside>

💡 [Read this article for an explanation of each of this redirections](https://catonmat.net/bash-one-liners-explained-part-three)

[The original cheatsheet for redirection operators can be found here:](https://catonmat.net/ftp/bash-redirections-cheat-sheet.pdf)

</aside>

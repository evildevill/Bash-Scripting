# Bash built-in commands

# ****Shell Builtins****

Built-in commands are distinct in that they do not require the execution of a child process. They were compiled into the shell and thus become part of its toolkit. There is no external program file to run them.

### Bash Built‐In Commands #-B

| Command | Description |
| --- | --- |
| .  | same as source builtin. Reads and executes commands from a designated file in the current shell |
| & | Starts a job in background mode |
| ((x)) | Evaluates the x mathematical expression |
| not: | Reads and executes commands from a designated file in the
current shell. |
| : | Does nothing, and always exits successfully, same as true builtin |
| [ t ] | Evaluates the t conditional expression |
| [[ e ]] | Evaluates the e conditional expression |
| alias | Defines an alias for the specified command |
| bg | Resumes a job in background mode |
| bind | Binds a keyboard sequence to a readline function or macro |
| break | Exits from a for , while , select , or until loop |
| builtin | Executes the specified shell built‐in command |

### Bash Built‐In Commands E-F

| echo | Displays the specified string to STDOUT |
| --- | --- |
| enable | Enables or disables the specified built‐in shell command |
| eval | Concatenates the specified arguments into a single command, and executes the command |
| exec | Replaces the shell process with the specified command |
| exit | Forces the shell to exit with the specified exit status |
| export | Sets the specified variables to be available for child shell processes |
| false | Sets a result to failed status |
| fc | Selects a list of commands from the history list |
| fg | Resumes a job in foreground mode |
| for | Executes set commands for every item in the list |
| function | Defines a shell script function |

### Bash Built‐In Commands G-P

| getopts | Parses the specified positional parameters |
| --- | --- |
| hash | Finds and remembers the full pathname of the specified command |
| help | Displays a help file |
| history | Displays the command history |
| if | Executes set commands based on conditional expression |
| jobs | Lists the active jobs |
| kill | Sends a system signal to the specified process ID (PID) |
| let | Evaluates each argument in a mathematical expression |
| local | Creates a limited‐scope variable in a function |
| logout | Exits a login shell |
| mapfile | Reads STDIN lines and puts them into an indexed array |
| popd | Removes entries from the directory stack |
| printf | Displays text using formatted strings |
| pushd | Adds a directory to the directory stack |
| pwd | Displays the pathname of the current working directory |

### Bash Built‐In Commands C-D

| caller | Returns the context of any active subroutine call |
| --- | --- |
| case | Selectively executes commands based on pattern |
| cd | Changes the current directory to the specified directory |
| command | Executes the specified command without the normal shell lookup |
| compgen | Generates possible completion matches for the specified word |
| complete | Displays how the specified words would be completed |
| compopt | Changes options for how the specified words would be completed |
| continue | Resumes the next iteration of a for , while , select , or until loop |
| coproc | Executes a coprocess |
| declare | Declares a variable or variable type |
| dirs | Displays a list of currently remembered directories |
| disown | Removes the specified jobs from the jobs table for the process |

## Bash Built‐In Commands R-#

| read | Reads one line of data from STDIN , and assigns it to a variable |
| --- | --- |
| readarray | Reads STDIN lines, and puts them into an indexed array |
| readonly | Reads one line of data from STDIN , and assigns it to a variable that can't be changed |
| return | Forces a function to exit with a value that can be retrieved by the calling script |
| select | Displays list of words with numbers allowing selection |
| set | Sets and displays environment variable values and shell attributes |
| shift | Rotates positional parameters down one position |
| shopt | Toggles the values of variables controlling optional shell behavior |
| source | Reads and executes commands from a designated file in the current shell |
| suspend | Suspends the execution of the shell until a SIGCONT signal is received |
| test | Returns an exit status of 0 or 1 based on the specified condition |
| time | Displays the accumulated real, user, and system times executing command(s) |
| times | Displays the accumulated user and system shell times |
| trap | Executes the specified command if the specified system signal is received |
| true | Sets a result to successful status |
| type | Displays how the specified word would be interpreted if used as a command |
| typeset | Declares a variable or variable type |
| ulimit | Sets a limit on the specified resource for system users |
| umask | Sets default permissions for newly created files and directories |
| unalias | Removes the specified alias |
| unset | Removes the specified environment variable or shell attribute |
| until | Executes set commands until condition statement returns true |
| wait | Waits for the specified process to complete, and returns the exit status |
| while | Executes set commands while condition statement returns true |
| { c; } | Group commands to execute within current shell |

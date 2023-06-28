# Bash options

<aside>
💡 Options are settings that change shell or script behavior. The `set` built-in command can be used to set options. There are two ways to set options  either by `set -o option-name` or, in short form, `set -option-abbrev` ****. To disable **an option, use `set +o option-name` ****or `set +option-abbrev` ****. To enable the option on a script on the command line use, `set +o option-name script-name`  ****or ****`set option-abbrev script-name`

</aside>

| Abbreviation | Name | Effect |
| --- | --- | --- |
| -B | brace expansion | Enable brace expansion (default setting = on) |
| +B | brace expansion | Disable brace expansion |
| -C | noclobber | Prevent overwriting of files by redirection (but this may  be overridden by >| ) |
| -D | (none) | List double-quoted strings prefixed by $, but do not execute commands in script |
| -a | allexport | Export all defined variables |
| -b | notify | Notify when jobs running in the background terminate (not of much use in a script) |
| -c … | (none) | Read commands from ... |
| checkjobs |  | Informs the user of any open jobs upon shell exit. Introduced in version 4 of Bash, and is still "experimental." Usage: shopt -s checkjobs (Caution: may hang!) |
| -e | errexit | Abort script at first error, when a command exits with non-zero status (except in until or while loops, if-tests, list constructs) |
| -f | noglob | Disable filename expansion (globbing) |
| globstar | globbing star-match | Enables the ** globbing operator. Usage: shopt -s globstar |
| -i | interactive | Runs a script in interactive mode |
| -n | noexec | Read commands in script, but do not execute them (syntax check) |
| -o Option-Name | (none) | Invoke the Option-Name option |
| -o posix | POSIX | Change the behavior of Bash, or invoked script, to conform to POSIX standard. |
| -o pipefail | pipe failure | Causes a pipeline to return the exit status of the last command in the pipe that returned a non-zero return value. |
| -p | privileged | Script runs as "suid" (caution!) |
| -r | restricted | Script runs in restricted mode |
| -s | stdin | Read commands from stdin |
| -t | onecmd | Exit after first command |
| -u | nounset | Attempt to use undefined variable outputs error message, and forces an exit |
| -v | verbose | Print each command to stdout before executing it |
| -x | xtrace | Similar to -v, but expands commands |
| - | (none) | End of options flag. All other arguments are positional parameters. |
| -- | (none) | Unset positional parameters. If arguments given (-- arg1 arg2), positional parameters set to arguments. |

<aside>
💡 [Read more about bash options](https://tldp.org/LDP/abs/html/options.html)

[More about bash options here](https://wiki.bash-hackers.org/commands/builtin/set)

</aside>

## Additional bash options

### Description

<aside>
💡 The `shopt` built-in command allows you to change additional shell optional behavior.

</aside>

### shopt options

| Option | Description |
| --- | --- |
| -o | Restrict the values of <OPTNAME…> to only those also known by the set builtin |
| -p | Print all shell options and their current value. Default. |
| -q | Quiet mode. Set exit code if named option is set. For multiple options: TRUE if all options are set, FALSE otherwise |
| -s | Enable (set) the shell options named by <OPTNAME…> or list all enabled options if no names are given |
| -u | Disabe (unset) the shell options named by <OPTNAME…> or list all disabled options 
if no names are given |

### shopt syntax

<aside>
🛠 `shopt [-pqsu] [-o] <OPTNAME...>`

</aside>

<aside>
💡 According to the options table, if only -s or -u are specified without any option names, only the currently enabled (-s) or disabled (-u) options are printed.

</aside>

### ****Exit code****

<aside>
💡 When listing options, the exit code is `TRUE` (0), if all options are enabled, `FALSE` otherwise.

When setting/unsetting an option, the exit code is `TRUE` unless the named option doesn't exitst.

</aside>

```bash
shopt -s nullglob  #Example to enable nullglob option
```

### ****List of additional shell options****

| Option name | Description |
| --- | --- |
| autocd | If set, a command name that is the name of a directory is executed as if it were the argument to the cd command. |
| cdspell | If set, minor errors in the spelling of a directory component in a cd command will be corrected. The errors checked for are transposed characters, a missing character, and one character too many. If a correction is found, the corrected file name is printed, and the command proceeds. |
| checkjobs | If set, Bash lists the status of any stopped and running jobs before exiting an interactive shell. If any jobs are running, this causes the exit to be deferred until a second exit is attempted without an intervening command. The shell always postpones exiting if any jobs are stopped. |
| dirspell | If set, Bash will perform spelling corrections on directory names to match a glob. |
| dotglob | If set, Bash includes filenames beginning with a . (dot) in the results of https://wiki.bash-hackers.org/syntax/expansion/globs. |
| nullglob | If set, Bash allows filename patterns which match no files to expand to a null string, rather than themselves. |
| failglob | If set, patterns which fail to match filenames during filename expansion result in an expansion error. |
| nocaseglob | If set, Bash matches filenames in a case-insensitive fashion when performing filename expansion. |
| globstar | If set, the pattern ‘**’ used in a filename expansion context will match all files and zero or more directories and subdirectories. If the pattern is followed by a ‘/’, only directories and subdirectories match. |

<aside>
  
💡 [Here is an exhaustive list of all the additional options](https://www.gnu.org/software/bash/manual/html_node/The-Shopt-Builtin.html)

</aside>

---

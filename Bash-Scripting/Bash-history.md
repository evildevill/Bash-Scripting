# Bash history

## History commands

| Command | Description |
| --- | --- |
| history | Display history |
| history n | Display only the last n commands from the history |
| history -c | Clears your current history and starts adding commands from scratch |
| history -d n | Delete the specified nth command from history |
| sudo !! | Run the previous command with sudo |
| <space> command | Prevent history from adding the command to history |
| shopt -s histverify | Don't execute expanded result immediately |
| echo $HISTSIZE | Display maximum of commands that can be stored in history file |

## History modifiers

| Modifiers | Description |
| --- | --- |
| <word>:h | Remove a trailing file name component, leaving only the head from the expanded command. |
| <word>:r | Remove a trailing suffix of the form .xxx, leaving the basename. |
| <word>:t | Remove all leading file name components, leaving the tail. |
| <word>:e | Remove all but the trailing suffix. |
| <word>:p | Print the new command but do not execute it. |
| <word>:q | Quote the substituted words, escaping further substitutions. |
| <word>:x | Quote the substituted words as with q, but break into words at blanks and newlines. The q and x modifiers are mutually exclusive; the last one supplied is used. |
| <word>:s/old/new/ | Substitute new for the first occurrence of old in the event line. |
| <word>:gs/old/new/ | Cause changes to be applied over the entire event line. This is used in conjunction with :s' |
| <word>:& | Repeat the previous substitution. |
| <word>:G | Apply the following s' or &' modifier once to each word in the event line. |

## History slices

| Slices | Description |
| --- | --- |
| !!:n | Expand only nth token from most recent command (command is 0; first argument is 1) |
| !^ | Expand first argument from most recent command |
| !$ | Expand last token from most recent command |
| !!:n-m | Expand range of tokens from most recent command |
| !!:n-$ | Expand nth token to last from most recent command |

## History event designators

| Event | Description |
| --- | --- |
| !! | Expand the previous command |
| !-n | Expand nth most recent command |
| !n | Expand nth command in history |
| !<command> | Expand most recent invocation of command <command> |
| !<text> | Expand the last command that begins with a specific text |
| !n:p or !<text>:p | Print the expanded command before executing it. |
| ^string1^string2 | Expand the last command, replacing string1 with string2. |
| !# | Expand the entire command line typed so far. |

## History Word designators

<aside>
💡 Word designators are used to select desired words from the event. A  colon “:” separates the event specification from the word designator.  Here are some word designators (^, $, *, -, or %)

</aside>

| Word | Description |
| --- | --- |
| !$ | Expand last parameter of most recent command |
| !* | Expand all parameters of most recent command |
| !^ | Expand the first parameter of the most recent command |
| !n | Expand nth command in history |
| !% | The first word matched by the most recent `?string?' search, if the search string begins with a character that is part of a word. |
| !x-y | A range of words; -y abbreviates 0-y |

<aside>
💡 Following the optional word designator, one or more of the modifiers listed on the left side may appear, each preceded by a ':'. These change or edit the word or words chosen from the history event. 

**Remove a trailing file name component, leaving only the head from the expanded command.**
`$ cat demo.sh`
`$ $!:h:p`  #⇒ this will print demo

</aside>

# Getting started

### Variables

```bash
NAME="WASII"

echo ${NAME}    # => WASII: This prints the variable value
echo $NAME      # => WASII: This prints the variable value
echo "$NAME"    # => WASII: This prints the variable value
echo '$NAME'    # => $NAME: This will print the Exact string, not the value.
echo "${NAME}!" # => WASII! : Concatenation of variable value with!

# Note: When declaring variables there should be no spaces between the variable
# name and equal sign and between the equal sign and the variable value.
# This will throw an error
NAME = "WASII"   # => Error (about space)

```

<aside>
💡 It is crucial to remember that when referencing a variable value, the dollar sign is used, but when referencing the variable to assign a value, the dollar sign is not used.

</aside>

### ****Special parameters****

| Parameter | Description |
| --- | --- |
| $1… $9 | Parameters 1 to 9. |
| $0 | Stores the name of the script file or the current shell name. |
| $1 | represents the first argument. |
| ${10} | Positional parameter 10. |
| $# | Number of positional parameters |
| $* | stores all the arguments. |
| $$ | Process id of the current shell. |
| $@ | All arguments, starting from first. |
| $- | Current options. |
| $_ | Last argument of the previous command |
| $! | The process ID (PID) of the most recently executed background pipeline (like started with command &) |
| $? | Status of the most recently executed foreground pipeline (exit/return code) |

<aside>
  
🔗 [Learn more about special parameters here:](https://wiki.bash-hackers.org/syntax/shellvars#special_parameters_and_shell_variables)

</aside>

### Comments

```bash
# This is an inline Bash comment.
: '
This is a
Multi-line comment
in bash

If it looks impeccable
'

# **Note you can replace the single quotations with** 
# **double qoutations**
```

<aside>
💡 For Multi-line comments use`:'` to open and `'`
 to close.

</aside>

### Functions

```bash
#!/usr/bin/env bash

get_username() {
    echo "WASII"
}

# Or using the function keyword
function get_username() {
    echo "WASII"
}

echo "You are $(get_username)"
```

### Brace Expansion

| Example  | Description |
| --- | --- |
| $ echo {A,B}.txt | the output will be A.txt and B.txt |
| {A,B} | Same as A B |
| {1..5} | Same as 1 2 3 4 5 |

<aside>
  
🔗 [Learn more about brace expansion here:](https://wiki.bash-hackers.org/syntax/expansion/brace)

</aside>

### Example script

```bash
#!/usr/bin/env bash

greet="world World"
echo "$greet!, I'm new here." 
# => Hello world! I'm new here.

#Execute the script

$ chmod +x helloworld.sh
$ ./helloworld.sh

# or just

$ bash helloworld.sh
```

### Conditions

```bash
#!/usr/bin/env bash

string="test"

if [[ -z "$string" ]]; then
    echo "String is empty"
elif [[ -n "$string" ]]; then
    echo "String is not empty"
fi
```

### Command Substitution

```bash
# => I'm WASII
echo "I'm $(whoami)"

# Similar to:
echo "I'm `whoami`"
```

<aside>
  
🔗 [Learn more about command substitution here:](https://wiki.bash-hackers.org/syntax/expansion/cmdsubst)

</aside>

---

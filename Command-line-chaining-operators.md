# Command line chaining operators

Below are some commonly used chaining operators which you can use with different commands:

| Chaining Operator | Description |
| --- | --- |
| & (Ampersand) | This sends a command, script, or process to the background. In short, it makes a command run in the background. |
| && (Logical AND) | The && operator will only execute the second command if the first command SUCCEEDS! , in other words, if the first command exits with a zero status. |
| || (Logical OR) | It's much more like an else statement in programming. The || will only execute the second command if the first command fails. In other words, if the first command exits with a non-zero status code. |
| ; (Semi-colon) | The command following this operator will execute even if the command preceding this operator is not successfully executed. |
| ! (NOT) | The NOT is much like the except statement. It will run all the commands except a given condition. It negates an expression within a command. |
| &&-|| (AND-OR) | It's a combination of the AND-OR operator. It's much like the if-else statement in programming. |
| | (Pipe) | The output of the command preceding this operator will act as an input of the command succeeding this operator. In other words, the output of another command will be given to the input of the other command. |
| >,>>, < (Input-OutputRedirection) | Redirects the output of a command or a group of commands to a file or stream. |
| \ (Concatenation) | Used to concatenate large commands over several lines in the shell. |
| () (Precedence) | Allows the commands to execute in precedence order. |
| {} (Combination) | The execution of the command succeeding this operator will depend on the execution of the first command. |

<aside>

💡 [Read more about command line chaining here:](https://linuxopsys.com/topics/bash-chain-operators-in-linux)

</aside>

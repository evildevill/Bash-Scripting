# Bash conditions and flow control

## ToDO

```bash
- switch statement in conditions and flow control
```

## Numeric conditions

| Condition | Description |
| --- | --- |
| [[ INTERGER1 -eq INTEGER2 ]]   | INTEGER1 is equal to INTEGER2 |
| [[ INTEGER1 -ne INTEGER2 ]] | INTEGER1 is not equal to INTEGER2 |
| [[ INTEGER1 -lt INTEGER ]] | INTEGER1 is less than INTEGER2 |
| [[ INTEGER1 -le INTEGER2 ]] | INTEGER1 is less than or equal to INTEGER2 |
| [[ INTEGER1 -gt INTEGER2 ]] | INTEGER1 is greater than INTEGER2 |
| [[ INTERGER1 -ge INTEGER2 ]] | INTEGER1 is greater than or equal to INTEGER2 |
| (( INTEGER1 < INTEGER2 )) | INTEGER1 is less than INTEGER2 |
| (( INTEGER1 <= INTEGER2 )) | INTEGER1 is less than INTEGER2 |
| (( INTEGER1 > INTEGER2 )) | INTEGER1 is greater than INTEGER2 |
| (( INTEGER1 >= INTEGER2 )) | INTEGER1 is greater than or equal to INTEGER2 |
| (( INTEGER1 == INTEGER2 )) | INTEGER1 is equal to INTEGER2 |
| (( INTEGER1 != INTEGER2 )) | INTEGER1 is not equal to INTEGER2 |

## String conditions

| Condition | Description |
| --- | --- |
| [[ -z STR ]] | Empty string |
| [[ -n STR ]] | Not empty string |
| [[ STR == STR ]] | Equal |
| [[ STR = STR ]] | Equal (Same above) |
| [[ STR < STR ]] | Less than (ASCII) |
| [[ STR > STR ]] | Greater than (ASCII) |
| [[ STR != STR ]] | Not Equal |
| [[ STR =~ REGEXP ]] | Regexp |

## More conditions

| Condition | Description |
| --- | --- |
| [[ -o noclobber ]] | If OPTION is enabled. |
| EXPR | expression is true |
| ! EXPR | negate expression |

## File conditions

| Condition | Expression |
| --- | --- |
| [[ -b FILE ]] | FILE exists and is block special |
| [[ -c FILE ]] | FILE exists and is character special |
| [[ -d FILE ]] | FILE exists and is a directory |
| [[ -e FILE ]] | FILE exists |
| [[ -f FILE ]] | FILE exists and is a regular file |
| [[ -g FILE ]] | FILE exists and is set-group-ID |
| [[ -G FILE ]] | FILE exists and is owned by the effective group ID |
| [[ -h FILE ]] | FILE exists and is a symbolic link (same as -L) |
| [[ -k FILE ]] | FILE exists and has its sticky bit set |
| [[ -L FILE ]] | FILE exists and is a symbolic link (same as -h) |
| [[ -N FILE ]] | FILE exists and has been modified since it was last read |
| [[ -O FILE ]] | FILE exists and is owned by the effective user ID |
| [[ -p FILE ]] | FILE exists and is a named pipe |
| [[ -r FILE ]] | FILE exists and the user has read access |
| [[ -s FILE ]] | FILE exists and has a size greater than zero |
| [[ -S FILE ]] | FILE exists and is a socket |
| [[ -t FD ]] | file descriptor FD is opened on a terminal |
| [[ -u FILE ]] | FILE exists and its set-user-ID bit is set |
| [[ -w FILE ]] | FILE exists and the user has write access |
| [[ -x FILE ]] | FILE exists and the user has execute (or search) access |
| [[ FILE1 -nt FILE2 ]] | FILE1 is newer (modification date) than FILE2 |
| [[ FILE1 -ot FILE2 ]] | FILE1 is older than FILE2 |
| [[ FILE1 -ef FILE2 ]] | FILE1 and FILE2 have the same device and inode numbers or both files are the same |

## Compound conditions

| Condition | Description |
| --- | --- |
| [[ condition1 ]] && [[ condition2 ]] | Evaluate to True if both conditions are TRUE |
| [[ condition1 ]] || [[ condition2 ]] | Evaluate to True if either one of the conditions TRUE |
| [ condition1 -a condition2 ] | Evaluate to True if both conditions are TRUE |
| [ condition1 -o condition2 ] | Evaluate to True if either one of the conditions TRUE |

<aside>
💡 Note: It is worth mentioning that you can replace all the double square brackets with single square brackets for example :  `[[ NUM -eq NUM ]]`   can also be written as `[ NUM -eq NUM ]` . This works with all the all conditions except for compound conditions which uses `-a` (AND) and `-o` (OR) as logical operators.

</aside>

## Advanced if-then Features

- Single parentheses `(.......)` allow you to use subshells in your if statement comparisons.
- The double parentheses `(( epression ))` command allows you to incorporate advanced mathematical formulas in your comparisons. [check out performing arithmetic operations.](Arithmetic%20operations%2068b9d24731e74ddebd71061e112b775a.md)
- The double bracket  `[[.......]]` command provides advanced features for string comparisons.

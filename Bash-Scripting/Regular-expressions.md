# Regular expressions

# Types of regular expressions

- The POSIX Basic Regular Expression (BRE)
- The POSIX Extended Regular Expression (ERE)

## Anchors

| ^ | Start of string, or start of line in multi-line pattern |
| --- | --- |
| \A | Start of string |
| $ | End of string, or end of line in multi-line pattern |
| \Z | End of string |
| \b | Word boundary |
| \B | Not word boundary |
| \< | Start of word |
| \> | End of word |
|  |  |

## Character classes

| [abc] | A single character of: a, b or c |
| --- | --- |
| [^abc] | A character except: a, b or c. The caret ^ negates character classes |
| [a-z] | A character in the range: a-z |
| [^a-z] | A character not in the range: a-z |
| [0-9] | A digit in the range: 0-9 |
| [a-zA-Z] | A character in the range:a-z or A-Z |
| [a-zA-Z0-9] | A character in the range:a-z, A-Z or 0-9 |
|  |  |
|  |  |

## Shorthand character classes

| \c | Control character |
| --- | --- |
| \s | White space |
| \S | Not white space |
| \d | Digit |
| \D | Not digit |
| \w | Word |
| \W | Not word |
| \x | Hexade­cimal digit |
| \O | Octal digit |

## Posix BRE Special Character Classes

| Class | Same as | Description |
| --- | --- | --- |
| [[:alnum:]] | [0-9A-Za-z] | Matches any alphanumeric character 0–9, A–Z, or a–z |
| [[:alpha:]] | [A-Za-z] | Matches any alphabetical character, either upper or lower case |
| [[:blank:]] | [\t ] | Matches a space or Tab character |
| [[:digit:]] | [0-9] | Matches a numerical digit from 0 through 9 |
| [[:graph:]] | [[:alnum:][:punct:]] | Visible characters (not space) |
| [[:lower:]] | [a-z] | Matches any lowercase alphabetical character a–z |
| [[:print:]] | [ -~] == [ [:graph:]] | Matches any printable character |
| [[:punct:]] | [!"#$%&’()*+,-./:;<=>?@[]^_`{|}~] | Matches a punctuation character |
| [[:space:]] | [\t\n\v\f\r ] | Matches any whitespace character: space, Tab, NL(newline), FF (formfeed), VT (vertical tab), CR (carriage return) |
| [[:upper:]] | [A-Z] | Matches any uppercase alphabetical character A–Z |
| [[:word:]] | [0-9A-Za-z_] | Matches all world characters |
| [[:xdigit:]] | [0-9A-Fa-f] | Matches all hexadecimal digits |
| [[:<:]] | [\b(?=\w)] | Matches start of word |
| [[:>:]] | [\b(?<=\w)] | Matches end of word |
| [[:ascii:]] | [\x00-\x7F] | ASCII codes 0-127 |
| [[:cntrl:]] | [\x00-\x1F\x7F] | Control characters |

## Quantifiers

| ? | Match an Element Zero or One Time |
| --- | --- |
| * | Match an Element Zero or More Times |
| + | Match an Element One or More Times |
| [0-9]+ | Any digit from 0-9 must appear 1 or more times. |
| {} | Match an Element a Specific Number of Times |
| a{m} | The character a must appear exactly m times. |
| a{m,n} | The character a must appear at least m times, but no more than n times. |
| a{m,} | The character a must appear m or more times. |
| a* | Greedy quantifier |
| a*? | Lazy quantifier |
| a*+ | Possessive quantifier |
| {,n} | Match the preceding element if it occurs no more than m times. |

<aside>
💡 **Common Meta-ch­ara­cters**
`^`                   `(`      `{`                `|`
`*`                   `<`      `$`                `)`
`?`                   `>`      `.`                `+`
`[`                   `\`                       
Escape these special characters with `\`

</aside>

## Groups and ranges

| . | Any character except new line (\n) |
| --- | --- |
| (a|b) | a or b |
| (...) | Group |
| (?:...) | Passive (non-c­apt­uring) group |
| [abc] | Range (a or b or c) |
| [^abc] | Not (a or b or c) |
| [a-q] | Lower case letter from a to q |
| [A-Q] | Upper case letter from A to Q |
| [0-7] | Digit from 0 to 7 |
| \x | Group/­sub­pattern number "­x" |

## Special Characters

| \n | Newline |
| --- | --- |
| \r | Carriage return |
| \t | Horizontal Tab |
| \v | Vertical Tab |
| \f | Form feed |
| \xxx | Octal character xxx |
| \xhh | Hex character hh |

## Pattern Modifiers

| g | Global match |
| --- | --- |
| i * | Case-i­nse­nsitive |
| m * | Multiple lines |
| s * | Treat string as single line |
| x * | Allow comments and whitespace in pattern |
| e * | Evaluate replac­ement |
| U * | Ungreedy pattern |

## Escape sequences

| \ | Escape following character |
| --- | --- |
| \Q | Begin literal sequence |
| \E | End literal sequence |

<aside>
💡 What is Escaping?

Escaping is a method of treating characters with special meanings in regular expressions literally rather than as special characters.

</aside>

## Assertions

| ?= | Lookahead assertion |
| --- | --- |
| ?! | Negative lookahead |
| ?<= | Lookbehind assertion |
| ?!= or ?<! | Negative lookbehind |
| ?> | Once-only Subexp­ression |
| ?() | Condition [if then] |
| ?()| | Condition [if then else] |
| ?# | Comment |

## String replacement

| $n | nth non-pa­ssive group |
| --- | --- |
| $2 | "­xyz­" in /^(abc­(xy­z))$/ |
| $1 | "­xyz­" in /^(?:a­bc)­(xyz)$/ |
| $` | Before matched string |
| $' | After matched string |
| $+ | Last matched string |
| $& | Entire matched string |

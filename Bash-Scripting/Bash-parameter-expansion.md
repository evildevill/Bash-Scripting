# Bash parameter expansion

## Syntax

| Syntax | Description |
| --- | --- |
| ${parameter%suffix} | Remove suffix |
| ${parameter#prefix} | Remove prefix |
| ${parameter%%suffix} | Remove long suffix |
| ${parameter##prefix} | Remove long prefix |
| ${parameter/pattern/string} | Replace first pattern match with string |
| ${parameter//pattern/string} | Replace all the pattern with string |
| ${parameter/%pattern/string} | Replace suffix pattern with string |
| ${parameter/#pattern/string} | Replace prefix patter with string |

## Substrings

| ${FOO:0:3} | Substring (position, length) |
| --- | --- |
| ${FOO:(-3):3} | Substring from the right |

## Length

| ${#FOO} | Length of $FOO |
| --- | --- |

## Default values

| ${FOO:-val} | $FOO, or val if unset |
| --- | --- |
| ${FOO:=val} | Set $FOO to val if unset |
| ${FOO:+val} | val if $FOO is set |
| ${FOO:?message} | Show message and exit if $FOO is unset |

## Substitution

```bash
echo ${food:-Cake}  #=> $food or "Cake"
STR="/path/to/foo.cpp"
echo ${STR%.cpp}    # /path/to/foo
echo ${STR%.cpp}.o  # /path/to/foo.o
echo ${STR%/*}      # /path/to

echo ${STR##*.}     # cpp (extension)
echo ${STR##*/}     # foo.cpp (basepath)

echo ${STR#*/}      # path/to/foo.cpp
echo ${STR##*/}     # foo.cpp

echo ${STR/foo/bar} # /path/to/bar.cpp

```

## B**asepath & Dirpath**

```bash
SRC="/path/to/foo.cpp"
BASEPATH=${SRC##*/}   
echo $BASEPATH  # => "foo.cpp"

DIRPATH=${SRC%$BASEPATH}
echo $DIRPATH   # => "/path/to/"

```

## Slicing

```bash
name="John"
echo ${name}           # => John
echo ${name:0:2}       # => Jo
echo ${name::2}        # => Jo
echo ${name::-1}       # => Joh
echo ${name:(-1)}      # => n
echo ${name:(-2)}      # => hn
echo ${name:(-2):2}    # => hn

length=2
echo ${name:0:length}  # => Jo

```

## **Transform**

```bash
STR="HELLO WORLD!"
echo ${STR,}   # => hELLO WORLD!
echo ${STR,,}  # => hello world!

STR="Hello world!"
echo ${STR^}   # => Hello world!
echo ${STR^^}  # => HELLO WORLD!

ARR=(hello World)
echo "${ARR[@],}" # => hello world
echo "${ARR[@]^}" # => Hello World

```

<aside>
💡 Read more about bash parameter expansions here:

</aside>

---

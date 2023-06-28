# Bash loops

## Bash for loop

```bash
for i in /etc/*; do
    echo $i
done

# Same as above(alternate syntax), also works with other loop structs
	
for i in /etc/* 
do
		echo $i
done
```

## Bash while loop

```bash
# incrementing the value
i=1
while [[ $i -lt 4 ]]; do
    echo "Number: $i"
    ((i++)) 
done

 # decrementing the value

i=3
while [[ $i -gt 0 ]]; do
    echo "Number: $i"
    ((i--))
done
```

## Continue statement

```bash

# seq command can be using to gerate ranges

for number in $(seq 1 3); do
    if [[ $number == 2 ]]; then
        continue;
    fi
    echo "$number"
done

```

## C-like for loop

```bash
for ((i = 0 ; i < 100 ; i++)); do
    echo $i
done 

# Same as above (alternate syntax) also works with other loop structs

for ((i = 0 ; i < 100 ; i++)) 
do
    echo $i
done 
```

## Bash while True loop

```bash
# while true long hand

while true; do
    # TODO
		# TODO
done

# or the shorthand (alternate syntax)

while :; do
    # TODO
		# TODO
done
```

## Break statement

```bash

`for number in $(seq 1 3); do
    if [[ $number == 2 ]]; then
        # Skip entire rest of loop or break out of the loop.
        break;
    fi
    # This will only print 1
    echo "$number"
done

```

## Ranges

```bash
for i in {1..10}; do
    echo "Number: $i"
done

# With step size
# => {START..STOP..STEP}

for i in {5..50..5}; do
    echo "Number: $i"
done
```

## Reading files with while loop

```bash
# using pipes

cat file.txt | while read line; do
    echo $line
done

# OR using input redirection

while read line; do
		echo $line
done < "/path/to/txt/file"

```

## Until or do loop

```bash
# incrementing
count=0
until [ $count -gt 10 ]; do
    echo "$count"
    ((count++))
done

# decremetning
count=10
until [ $count -eq 0 ]; do
    echo "$count"
    ((count--))
done
```

---

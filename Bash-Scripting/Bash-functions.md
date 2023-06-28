# Bash functions

## **Defining functions**

```bash
greet() {
    echo "hello $1 $2"
}

# Same as above (alternate syntax)
function greet() {
    echo "hello $1 $2"
}

# Calling the function
greet "John" "Paul"
```

## **Returning values**

```bash
add_numbers() {

		# perfoming mathematical additions
    local result=$(( $1 + $2)
		
		# returning the sresult value
    echo $result
}

# storing the returned value
result="$(add_numbers 1 2)"
```

## Raising errors

```bash
# using return
myfunc() {
    return 1
}

if myfunc; then
    echo "success"
else
    echo "failure"
fi
```

---

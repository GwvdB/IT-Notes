# Bash Scripting for Linux

**Bash scripting** is a powerful way to automate tasks in Linux, allowing you to execute multiple commands, handle file operations, and perform repetitive tasks efficiently.

## Table of Contents

- [[#What is Bash Scripting]]
- [[#Basic Structure of a Bash Script]]
- [[#Variables in Bash]]
- [[#Conditional Statements]]
- [[#Loops in Bash]]
- [[#Functions in Bash]]
- [[#Examples of Bash Scripts]]

---

# What is Bash Scripting

Bash, or **Bourne Again SHell**, is a command language interpreter for Linux. Bash scripting involves creating a text file with a series of Bash commands, allowing for automation of tasks and customization of workflows.

Bash scripts are commonly used for:
- Automating repetitive tasks
- Managing files and directories
- Handling system processes
- Configuring environments and installing packages

---

# Basic Structure of a Bash Script

A Bash script is a text file that contains a sequence of commands, typically starting with a **shebang** (`#!`) that indicates the interpreter. 

### Sample Bash Script
```bash
#!/bin/bash
# This is a comment
echo "Hello, World!"
```

### Executing a Bash Script
1. **Make the script executable**:
   ```bash
   chmod +x script_name.sh
   ```
2. **Run the script**:
   ```bash
   ./script_name.sh
   ```

---

# Variables in Bash

Variables in Bash allow you to store and retrieve values. Variable names are case-sensitive and can store strings, integers, and more.

### Creating Variables
```bash
name="John"
number=42
```

### Accessing Variables
To access a variable’s value, use the `$` symbol:
```bash
echo "Name: $name, Number: $number"
```

### Special Variables
- `$0`: The name of the script.
- `$1`, `$2`, etc.: Positional arguments passed to the script.
- `$#`: Number of arguments passed.
- `$@`: All arguments passed to the script.

---

# Conditional Statements

Conditional statements enable decision-making in Bash scripts. Common conditional statements include **if**, **else**, **elif**, and **case**.

### Basic If Statement
```bash
if [ "$name" == "John" ]; then
  echo "Hello, John!"
else
  echo "Hello, stranger!"
fi
```

### Case Statement
A `case` statement is useful for matching a variable against multiple patterns.
```bash
case $1 in
  start)
    echo "Starting the program."
    ;;
  stop)
    echo "Stopping the program."
    ;;
  *)
    echo "Unknown command."
    ;;
esac
```

---

# Loops in Bash

Loops allow you to iterate through items or execute commands repeatedly. Common loops include **for**, **while**, and **until**.

### For Loop
```bash
for i in {1..5}; do
  echo "Number $i"
done
```

### While Loop
```bash
count=1
while [ $count -le 5 ]; do
  echo "Count is $count"
  ((count++))
done
```

### Until Loop
```bash
count=5
until [ $count -le 0 ]; do
  echo "Countdown: $count"
  ((count--))
done
```

---

# Functions in Bash

Functions in Bash scripts allow you to group commands and reuse code. They are defined once and called whenever needed.

### Defining and Calling a Function
```bash
greet() {
  echo "Hello, $1!"
}

# Call the function
greet "Alice"
```

Functions help keep scripts organized and prevent code repetition.

---

# Examples of Bash Scripts

Here are some examples of useful Bash scripts to get started with common tasks.

### Example 1: Backup Script
```bash
#!/bin/bash
# Backup script to copy a directory

source_dir="/path/to/source"
backup_dir="/path/to/backup"

echo "Starting backup..."
cp -r "$source_dir" "$backup_dir"
echo "Backup completed!"
```

### Example 2: Disk Usage Checker
```bash
#!/bin/bash
# Checks disk usage and warns if usage exceeds a limit

threshold=80
usage=$(df / | grep / | awk '{print $5}' | sed 's/%//g')

if [ $usage -gt $threshold ]; then
  echo "Warning: Disk usage exceeded $threshold%!"
else
  echo "Disk usage is under control."
fi
```

### Example 3: Simple Calculator
```bash
#!/bin/bash
# Simple calculator for addition and subtraction

echo "Enter first number: "
read num1
echo "Enter second number: "
read num2
echo "Choose operation (+ or -): "
read op

if [ "$op" == "+" ]; then
  result=$((num1 + num2))
elif [ "$op" == "-" ]; then
  result=$((num1 - num2))
else
  echo "Invalid operation!"
fi

echo "Result: $result"
```
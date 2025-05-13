#linux #commands #text-processing #file-operations

The `sort` command in Linux is used to sort text files line by line. See also [[Linux-Commands#Text Manipulation]].

## Basic Syntax
```bash
sort [OPTIONS] [FILE(s)]
```

## Common Usage Patterns

### Basic Sort
```bash
sort file.txt
```

### Numeric Sort
```bash
sort -n numbers.txt
```

### Reverse Sort
```bash
sort -r file.txt
```

### Month Sort
```bash
sort -M dates.txt
```

## Options

### Sort Types
- `-n`: Numeric sort
- `-h`: Human numeric sort (2K, 1G)
- `-M`: Month sort
- `-V`: Version number sort
```bash
# Numeric sort
sort -n numbers.txt

# Human readable numbers
sort -h sizes.txt

# Version numbers
sort -V versions.txt
```

### Sort Direction
- `-r`: Reverse order
- `-R`: Random sort (shuffle)
```bash
# Reverse sort
sort -r file.txt

# Random order
sort -R file.txt
```

### Field Options
- `-k`: Sort by specific field
- `-t`: Field separator
- `-b`: Ignore leading blanks
```bash
# Sort by second field
sort -k2 file.txt

# Sort by : separated field
sort -t: -k3 /etc/passwd
```

### Output Control
- `-u`: Unique lines only
- `-f`: Ignore case
- `-o`: Output to file
```bash
# Remove duplicates
sort -u file.txt

# Case insensitive
sort -f file.txt

# Save to new file
sort -o output.txt input.txt
```

## Common Scenarios

### Log Analysis
```bash
# Sort log entries by date
sort -k1,2 logfile.txt

# Sort unique IP addresses
sort -u -t' ' -k1,1 access.log
```

### Data Processing
```bash
# Sort CSV by column
sort -t',' -k2 data.csv

# Sort and remove duplicates
sort -u numbers.txt
```

### System Administration
```bash
# Sort users by UID
sort -t: -k3 -n /etc/passwd

# Sort processes by memory usage
ps aux | sort -k4 -r
```

## Error Handling

### Common Errors
1. Memory Issues
   ```bash
   # Use temporary directory
   sort -T /tmp bigfile.txt
   ```

2. Invalid Number Format
   ```bash
   # Check format first
   grep '^[0-9]' file.txt | sort -n
   ```

3. Field Specification
   ```bash
   # Correct field format
   sort -k2,2 file.txt
   ```

## Best Practices

### Performance
1. Use appropriate sort type
2. Consider memory usage
3. Use -S for buffer size
4. Use -T for temp directory

### Data Handling
1. Verify input format
2. Check field separators
3. Consider case sensitivity
4. Validate output

## Scripting Examples

### Basic Sort Script
```bash
#!/bin/bash
# Sort and deduplicate data
input="data.txt"
output="sorted.txt"

sort -u "$input" > "$output" || {
    echo "Sort failed"
    exit 1
}
```

### Advanced Sorting
```bash
#!/bin/bash
sort_logs() {
    local input="$1"
    local output="$2"
    
    sort -t'|' \
         -k1,1 \
         -k2,2n \
         "$input" > "$output"
}

sort_logs "input.log" "sorted.log"
```

## System Integration

### Log Processing
```bash
# Sort and count unique entries
sort access.log | uniq -c | sort -nr

# Sort by timestamp
sort -k1,2 -t'[' syslog
```

### File Organization
```bash
# Sort directory listing
ls -l | sort -k5 -n

# Sort by file extension
ls | sort -t. -k2
```

## Related Commands
- [[Linux-Commands#Text Processing|uniq]] - Remove duplicates
- [[Linux-Commands#Text Processing|grep]] - Pattern matching
- [[Linux-Commands#Text Processing|awk]] - Text processing
- [[Linux-Commands#File Operations|cut]] - Extract fields

## Quick Reference

### Common Commands
```bash
# Basic sort
sort file.txt

# Numeric sort
sort -n numbers.txt

# Sort by field
sort -k2 file.txt

# Unique sort
sort -u file.txt

# Reverse sort
sort -r file.txt
```

### Field Specifications
```bash
# Sort by first field
sort -k1,1 file.txt

# Sort by multiple fields
sort -k1,1 -k2,2n file.txt

# Sort with delimiter
sort -t: -k3,3n file.txt
```

## Tips and Tricks
1. Use -s for stable sort
2. Combine with uniq for counting
3. Use -z for null-terminated lines
4. Remember field numbering starts at 1

### Common Combinations
```bash
# Sort and count
sort file.txt | uniq -c

# Sort multiple files
sort file1.txt file2.txt > sorted.txt

# Sort and merge
sort -m sorted1.txt sorted2.txt
```
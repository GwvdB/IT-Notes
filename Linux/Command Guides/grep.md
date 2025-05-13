#linux #commands #text-processing #search

The `grep` command in Linux is used for searching text patterns using regular expressions. See also [[Linux-Commands#Text Manipulation]].

## Basic Syntax
```bash
grep [OPTIONS] PATTERN [FILE(s)]
```

## Common Usage Patterns

### Basic Search
```bash
grep "pattern" file.txt
```

### Case-Insensitive Search
```bash
grep -i "pattern" file.txt
```

### Recursive Search
```bash
grep -r "pattern" directory/
```

### Show Line Numbers
```bash
grep -n "pattern" file.txt
```

## Options

### Pattern Matching
- `-i`: Case insensitive search
- `-w`: Match whole words only
- `-x`: Match whole lines only
- `-F`: Fixed strings (no regex)
- `-E`: Extended regex
```bash
# Case insensitive
grep -i "error" log.txt

# Whole word only
grep -w "test" file.txt

# Fixed string
grep -F "a.b.c" file.txt
```

### Output Control
- `-n`: Show line numbers
- `-c`: Count matches only
- `-l`: Show only filenames
- `-v`: Invert match
- `-o`: Show only matched parts
```bash
# Show line numbers
grep -n "error" log.txt

# Count matches
grep -c "error" log.txt

# Show matching files
grep -l "pattern" *.txt
```

### Directory Search
- `-r`: Recursive search
- `-R`: Recursive (follow symlinks)
- `--exclude`: Skip files
- `--include`: Search only specific files
```bash
# Recursive search
grep -r "TODO" src/

# Include only .py files
grep -r --include="*.py" "def" src/
```

### Context Control
- `-A n`: Show n lines after
- `-B n`: Show n lines before
- `-C n`: Show n lines around
```bash
# Show 3 lines around match
grep -C 3 "error" log.txt
```

## Common Scenarios

### Log Analysis
```bash
# Find errors in logs
grep -i "error" /var/log/syslog

# Show errors with context
grep -B 2 -A 2 "exception" app.log
```

### Code Search
```bash
# Find function definitions
grep -r "^def" *.py

# Find TODO comments
grep -r -n "TODO:" src/
```

### Configuration Search
```bash
# Find settings
grep -r "ENABLED" /etc/

# Check service status
grep "Active" /etc/systemd/system/*.service
```

## Error Handling

### Common Errors
1. Binary File Matches
   ```bash
   # Text files only
   grep -I "pattern" *
   ```

2. Permission Denied
   ```bash
   # Use sudo for restricted files
   sudo grep "root" /etc/shadow
   ```

3. Invalid Regex
   ```bash
   # Use fixed strings
   grep -F "[bracket]" file.txt
   ```

## Best Practices

### Search Efficiency
1. Use appropriate options
2. Narrow search scope
3. Consider using ripgrep for large codebases
4. Use fixed strings when possible

### Pattern Writing
1. Start simple, refine as needed
2. Test patterns on sample data
3. Use word boundaries when appropriate
4. Consider case sensitivity

## Scripting Examples

### Basic Search Script
```bash
#!/bin/bash
# Search for pattern in logs
pattern="error"
logfile="/var/log/syslog"

grep -i "$pattern" "$logfile" || {
    echo "No matches found"
    exit 1
}
```

### Advanced Search
```bash
#!/bin/bash
search_code() {
    local pattern="$1"
    local dir="${2:-.}"
    
    grep -r \
         --include="*.{py,js,cpp}" \
         -n \
         "$pattern" \
         "$dir"
}

search_code "TODO"
```

## System Integration

### Log Monitoring
```bash
# Monitor errors in real time
tail -f log.txt | grep --line-buffered "error"

# Count errors by type
grep -oP 'error: \K.*' log.txt | sort | uniq -c
```

### Security Auditing
```bash
# Check for failed logins
grep "Failed password" /var/log/auth.log

# Find unauthorized sudo usage
grep "sudo:" /var/log/auth.log
```

## Related Commands
- [[Linux-Commands#Text Processing|awk]] - Text processing
- [[Linux-Commands#Text Processing|sed]] - Stream editor
- [[Linux-Commands#File Operations|find]] - File search
- [[Linux-Commands#Text Processing|sort]] - Sort text

## Quick Reference

### Common Commands
```bash
# Basic search
grep "pattern" file.txt

# Recursive search
grep -r "pattern" dir/

# Case insensitive
grep -i "pattern" file.txt

# Line numbers
grep -n "pattern" file.txt

# Count matches
grep -c "pattern" file.txt
```

### Regular Expression Examples
```bash
# Start of line
grep "^start" file.txt

# End of line
grep "end$" file.txt

# Either/or
grep "this\|that" file.txt

# Any single character
grep "te.t" file.txt
```

## Tips and Tricks
1. Use `-v` to exclude patterns
2. Combine with pipes for complex filtering
3. Use context options for better understanding
4. Remember to quote patterns

### Common Combinations
```bash
# Find and replace with sed
grep -l "old" *.txt | xargs sed -i 's/old/new/g'

# Search and process with awk
grep "pattern" file.txt | awk '{print $2}'

# Search compressed files
zgrep "pattern" file.gz
```
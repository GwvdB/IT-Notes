#linux #commands #process-management #system-administration

The `ps` (process status) command in Linux is used to list information about running processes, including their process ID, user, CPU and memory usage, and more. See also [[Linux-Commands#System Status]].

## Basic Syntax
```
ps [OPTIONS]
```

## Common Usage Patterns

### List All Running Processes
```bash
ps
ps -e
ps aux
```

### List Processes for Current User
```bash
ps
ps -u
ps -U username
```

### List Processes by Process ID
```bash
ps -p PID
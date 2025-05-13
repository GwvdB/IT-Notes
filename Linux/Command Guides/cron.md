#linux #commands #system #scheduling

The `cron` system in Linux is used for scheduling automated tasks. See also [[Linux-Commands#System]].

## Basic Syntax
```bash
crontab [OPTIONS] FILE
```

## Crontab Format
```bash
# m h dom mon dow command
* * * * * command_to_execute
```
- m: minute (0-59)
- h: hour (0-23)
- dom: day of month (1-31)
- mon: month (1-12 or JAN-DEC)
- dow: day of week (0-6 or SUN-SAT)

## Common Usage Patterns

### Edit Crontab
```bash
crontab -e
```

### List Crontab
```bash
crontab -l
```

### Remove Crontab
```bash
crontab -r
```

## Options

### Edit (-e)
```bash
crontab -e
```
- Edit user's crontab

### List (-l)
```bash
crontab -l
```
- Display crontab entries

### Remove (-r)
```bash
crontab -r
```
- Delete user's crontab

### Edit User (-u)
```bash
crontab -u username -e
```
- Edit another user's crontab

## Common Time Patterns

### Time Specifications
```bash
# Every minute
* * * * *

# Every hour
0 * * * *

# Every day at midnight
0 0 * * *

# Every Sunday
0 0 * * 0

# Every first of month
0 0 1 * *
```

## Common Scenarios

### Scheduled Tasks
```bash
# Daily backup at 2 AM
0 2 * * * /backup/script.sh

# Weekly cleanup on Sunday
0 0 * * 0 /cleanup/weekly.sh

# Every 15 minutes
*/15 * * * * /scripts/check.sh
```

## System Directories

### Cron Locations
```bash
/etc/crontab          # System crontab
/etc/cron.d/          # System cron jobs
/etc/cron.daily/      # Daily jobs
/etc/cron.hourly/     # Hourly jobs
/etc/cron.monthly/    # Monthly jobs
/etc/cron.weekly/     # Weekly jobs
```

## Best Practices

### Usage Guidelines
1. Use full paths in scripts
2. Redirect output to logs
3. Set appropriate permissions
4. Test scripts manually first

### Security Considerations
1. Limit cron access
2. Log cron activities
3. Review cron jobs regularly
4. Use restricted paths

## Quick Reference

### Common Commands
```bash
# Edit crontab
crontab -e

# List jobs
crontab -l

# Remove all jobs
crontab -r

# Edit specific user
crontab -u user -e
```

## Related Commands
- [[Linux-Commands#System|at]] - One-time task scheduling
- [[Linux-Commands#System|systemd-timer]] - Systemd timer units
- [[Linux-Commands#System|anacron]] - Non-real-time job scheduler
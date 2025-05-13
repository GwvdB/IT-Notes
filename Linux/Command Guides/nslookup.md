#linux #commands #networking #dns

The `nslookup` command in Linux queries DNS servers for DNS lookup information. See also [[Linux-Commands#Networking]].

## Basic Syntax
```bash
nslookup [OPTIONS] {hostname|IP} [server]
```

## Common Usage Patterns

### Basic Lookup
```bash
nslookup example.com
```

### Specify DNS Server
```bash
nslookup example.com 8.8.8.8
```

### Reverse Lookup
```bash
nslookup 8.8.8.8
```

## Options

### Query Type (-type=)
```bash
nslookup -type=mx domain.com
```
- Common types: A, AAAA, MX, NS, SOA, TXT

### Debug Mode (-debug)
```bash
nslookup -debug domain.com
```
- Show detailed query information

### Query Timeout (-timeout=)
```bash
nslookup -timeout=10 domain.com
```
- Set query timeout

## Interactive Mode Commands
```bash
> server 8.8.8.8        # Change server
> set type=mx           # Set record type
> set debug             # Enable debugging
> exit                  # Exit interactive mode
```

## Common Scenarios

### DNS Troubleshooting
```bash
# Check MX records
nslookup -type=mx gmail.com

# Verify nameservers
nslookup -type=ns domain.com

# Check reverse DNS
nslookup IP_ADDRESS
```

## Best Practices

### Usage Guidelines
1. Verify DNS server responses
2. Check multiple record types
3. Use timeout for slow responses
4. Document query results

## Quick Reference

### Common Commands
```bash
# Basic lookup
nslookup domain.com

# MX record lookup
nslookup -type=mx domain.com

# Using specific DNS server
nslookup domain.com 8.8.8.8
```

## Related Commands
- [[Linux-Commands#Networking|dig]] - DNS lookup tool
- [[Linux-Commands#Networking|host]] - DNS lookup utility
- [[Linux-Commands#Networking|whois]] - Domain information
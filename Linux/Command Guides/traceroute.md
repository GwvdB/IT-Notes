#linux #commands #networking #diagnostics

The `traceroute` command in Linux traces the route that packets take to a network host. See also [[Linux-Commands#Networking]].

## Basic Syntax
```bash
traceroute [OPTIONS] HOST
```

## Common Usage Patterns

### Basic Trace
```bash
traceroute example.com
```

### Specify Protocol
```bash
traceroute -I example.com  # ICMP
traceroute -T example.com  # TCP
traceroute -U example.com  # UDP
```

## Options

### ICMP Echo (-I)
```bash
traceroute -I hostname
```
- Use ICMP ECHO for probes

### TCP SYN (-T)
```bash
traceroute -T hostname
```
- Use TCP SYN for probes

### Port Number (-p)
```bash
traceroute -p 80 hostname
```
- Specify port number

### Maximum TTL (-m)
```bash
traceroute -m 30 hostname
```
- Set maximum hops

### Wait Time (-w)
```bash
traceroute -w 5 hostname
```
- Set wait time seconds

## Common Scenarios

### Network Troubleshooting
```bash
# Check connection path
traceroute -I google.com

# Debug routing issues
traceroute -T -p 80 website.com

# Multiple protocols
traceroute -I host && traceroute -T host
```

## Best Practices

### Usage Guidelines
1. Use with firewall consideration
2. Try different protocols
3. Consider timeouts
4. Document results

## Quick Reference

### Common Commands
```bash
# Basic trace
traceroute hostname

# ICMP trace
traceroute -I hostname

# TCP trace to port 80
traceroute -T -p 80 hostname
```

## Related Commands
- [[Linux-Commands#Networking|ping]] - Test connectivity
- [[Linux-Commands#Networking|mtr]] - Combined trace and ping
- [[Linux-Commands#Networking|nslookup]] - DNS query
#linux #commands #networking #troubleshooting

The `ping` command in Linux is used to test the reachability of a network host or device. It sends ICMP (Internet Control Message Protocol) echo request packets to the target and waits for a response. See also [[Linux-Commands#Network Information]]

## Basic Syntax
```
ping [OPTIONS] HOST
```

## Common Usage Patterns

### Ping a Host
```bash
ping example.com
ping 192.168.1.1
```

### Ping a Host Continuously
```bash
ping -c 5 example.com
ping -i 2 example.com
```

### Ping with Specific Packet Size
```bash
ping -s 1024 example.com
```

### Ping and Resolve Hostnames
```bash
ping -n example.com
```

### Ping and Display Statistics
```bash
ping -s example.com
```

## Options

### Count (-c)
```bash
ping -c 5 example.com
```
- Sends the specified number of packets and then stops

### Interval (-i)
```bash
ping -i 2 example.com
```
- Sets the wait interval between packets (in seconds)

### Packet Size (-s)
```bash
ping -s 1024 example.com
```
- Sets the size of the packets sent (in bytes
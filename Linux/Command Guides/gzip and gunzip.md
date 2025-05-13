#linux #commands #file-compression

The `gzip` and `gunzip` commands in Linux are used for file compression and decompression. See also [[Linux-Commands#File Operations]].

## Basic Syntax
```bash
gzip [OPTIONS] FILE(S)
gunzip [OPTIONS] FILE(S)
```

## Common Usage Patterns

### Compress File
```bash
gzip filename
```

### Decompress File
```bash
gunzip filename.gz
```

### Multiple Files
```bash
gzip file1 file2 file3
```

## Options

### Keep Original (-k)
```bash
gzip -k filename
```
- Keep input files

### Compression Level (-#)
```bash
gzip -9 filename
```
- Set compression level (1-9)

### Test (-t)
```bash
gzip -t filename.gz
```
- Test compressed file integrity

### Verbose (-v)
```bash
gzip -v filename
```
- Display compression ratio

## Common Scenarios

### File Compression
```bash
# Maximum compression
gzip -9 large_file

# Keep original
gzip -k important_file

# Compress directory
tar cz directory | gzip > backup.tar.gz
```

### File Decompression
```bash
# Decompress single file
gunzip file.gz

# Decompress multiple files
gunzip *.gz

# View without decompressing
zcat file.gz
```

## Best Practices

### Usage Guidelines
1. Use appropriate compression level
2. Keep originals when needed
3. Check file integrity
4. Monitor disk space

### File Handling
1. Compress similar files together
2. Use meaningful extensions
3. Monitor compression ratios
4. Regular integrity checks

## Quick Reference

### Common Commands
```bash
# Compress file
gzip file

# Decompress file
gunzip file.gz

# Maximum compression
gzip -9 file

# Keep original
gzip -k file
```

## Related Commands
- [[Linux-Commands#File Operations|bzip2]] - Alternative compression
- [[Linux-Commands#File Operations|tar]] - Archive files
- [[Linux-Commands#File Operations|zip]] - ZIP compression
Conditional statements allow programs to make decisions based on certain conditions. **If**, **else**, and **else if** statements execute different code depending on whether conditions are true or false.

The conditional statements add variability to programming. It lets a program do a variety of things.

## If Statements

Most languages use () <-- what's inside is evaluated as *true* or *false*.

```
if (___ is true)
	{do ___}
```

## Else-If Statement

If the 'if' statement is false, the 'else-if' statement is run. If the 'else-if' statement is false it is also bypassed.

These can get quite messy, so it's possible to use 'switch' statements instead. (This is a collapsible way to write many 'if-else' statements).

## Else Statement

Usually comes after the 'if'/'else-if statements. This instruction will **always** carry out, even if the previous statements are false.

### Example 

Python
```
if age > 18:
    print("Adult")
else if age = 18:
	print("New Adult")
else:
    print("Minor")
```

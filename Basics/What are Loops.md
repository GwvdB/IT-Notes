Loops execute a block of code repeatedly until a specified condition is met. Common loops include **for** and **while** loops.

### Example

python
```
for i in range(5):
	print(i)
```

## For Loop

- This is used to carry out a set of instructions numerous times.
- There are 3 parts
	- Integer value
	- Conditional Statement
	- An operation to modify the Integer value after the instructions are completed
- A condition **must** be set that can be met. Or an infinite loop will happen and this can crash the program.

### Example

```
{
Countries = ['Canada', 'France', 'USA']
	for country in Countries
		print ('Welcome to', country)
}
```

## For Each Loop

This is used for iterating through entire arrays. The loop will go through each individual array and carry out a set of instructions for each. Perfect for performing operations across entire collections.

## While Loop

This is continuously run as long as the conditional statement is true. It is similar to a 'for loop' but it can be used for an infinite loop.

## Do-While Loop

Similar to a While Loop but it will still run at least once even if the condition is false, otherwise it will continue to loop as long as the condition is true.
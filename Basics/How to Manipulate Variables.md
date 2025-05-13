Manipulating variables includes assigning, updating, or reusing stored data. You can perform operations like addition, concatenation, or logical comparisons depending on the data type.

When a line of code is created **(and is executed)** a space in memory stores the variable name + content. Once the code is run the memory is deleted until it is run again where a new space is made. A variable can also be created with no information which an end-user can fill in at a later time. This is an example of the ability of consistently updating variables.

When trying to access an empty variable this will result in a **NullPointerException**. This is an error that occurs when trying to access something that doesn't exist. Usually one wants to avoid this.

A variable can be set to read the information from another variable. This does not create space in memory as the space is already occupied elsewhere.
#### Example
```
channelName = name;
Name = "Name Here"
```

### Example

Python
```
x = 10
x = x + 5  # Updates x to 15
```

## Naming Variables

Variables must always be a continuous String. CamelCase is typically what is used. This is where the first word is not capitalised but every words consecutively is. E.G. employeeLastNames.
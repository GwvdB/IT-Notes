A data type that represents a single unit of text, such as a letter (`A`, `z`), a digit (`5`, `9`), a punctuation mark (`!`, `?`), or even a special symbol (`@`, `#`). Characters are typically enclosed in single quotes, like `'A'` or `'5'`, in many programming languages.

### Characteristics of Characters:

1. **Single Unit**: Characters are designed to hold only one symbol at a time. They cannot represent multiple symbols or letters, as that would make them a string.
2. **Stored as Code**: Under the hood, characters are often stored as numerical codes based on character encoding standards, such as ASCII or Unicode. For example, in ASCII, the character `'A'` has a code of 65.

### Common Uses of Characters:

- **Single Letters or Symbols**: Characters are used when only one symbol or letter is required, such as representing a grade (`'A'`, `'B'`).
- **Character Processing**: They are often used in contexts where individual character manipulation is necessary, such as iterating through a string character-by-character.

### Example in Code:

1. **In C/C++**:
```
char letter = 'A';  // Represents the character 'A'
```
2. **In Java**:
```
char symbol = '$';  // Represents the character '$'
```    

### Characters vs. Strings:

- **Character**: Holds a single symbol (e.g., `'A'`).
- **String**: Holds a sequence of characters (e.g., `"Hello"`).
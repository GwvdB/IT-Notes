The rules governing the correct structure and composition of statements in a programming language, including the arrangement of symbols, keywords, operators, and punctuation.

Syntax is essential because, without it, the language's compiler or interpreter wouldn't be able to parse or understand the code. Syntax errors occur when code doesn’t follow these rules
## Levels of Syntax (often conceptualised in three parts):

There are various ways to describe the levels of syntax in programming languages, but here is a common breakdown:

1. **Lexical Syntax (Lexical Structure)**:    
    - Defines the smallest elements of the language, such as tokens, keywords, operators, and symbols.
    - Covers the **spelling** of identifiers (variable names, keywords, literals) and rules like capitalisation, white-space, and how tokens are combined to form valid symbols.
    
1. **Concrete Syntax (Grammatical Structure)**:
    - Deals with the formal grammar of the language, defining how tokens combine to form valid statements and expressions.
    - This includes the **grammar rules** that govern statements like assignments, loops, function calls, etc. For example, it specifies the order in which statements must appear (like `if` conditionals followed by `{}` for blocks in some languages).
    
1. **Abstract Syntax (Structural Representation)**:
    - Focuses on the structure of the code after removing syntactic "noise" (such as parentheses or brackets used only for grouping).
    - The abstract syntax typically represents the code in terms of its logical structure (e.g., using an abstract syntax tree, or AST), making it easier to understand relationships between code components like expressions and statements.
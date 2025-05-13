The process of identifying and extracting common features or patterns from objects, functions, or procedures, focusing on high-level functionality while hiding underlying complexity. It allows us to simplify complex systems by modelling essential properties and ignoring irrelevant details.

# Example
If there are two functions that perform similar tasks with minor differences, a more general function that captures their shared functionality can be created. For instance:

- Suppose `functionA` and `functionB` both perform similar mathematical operations but differ slightly in how they operate on input data.
- A new `generalFunction` can be created that includes parameters to handle both cases, combining the logic of `functionA` and `functionB` into a single, reusable function.
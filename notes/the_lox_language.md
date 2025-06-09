# The Lox Language
```
// Your first lox program
print "Hello World";
```
My first thoughts:
- The right way to do comments  
- No paranthesis on function calls
- Semi colon to end 
- Quotes from strings

## Other things about the language
1. Dynamically typed
2. Garbage collected
3. Data types:
    - booleans
    - numbers (only double precision floating point)
    - strings
    - nil
4. Expressions
    - arithmatic
    - negate
    ```
    -negateMe
    ```
    - Comparison and equality
    - Logical operators 
    ```
    !true // false
    ```
    - Precedence and grouping
5. Statements
    - print
    ```
    "some expression"; 
    ```
    ```
    // wrap in 1 block
    {
        print "One statement";
        print "Two statements";
    }
    ```
6. Variables
    - var keyword
    ```
    var varibleName = "value";
    var nilVar; // nil
    ```
7. Control flow
    - if / else
    ```
    if (condition) {
        print "yes";
    } else {
        print "no";
    }
    ```
    - while loop
    - for loop
8. Function calls
    - same as in C
    - when defining we use fun keyword
9. Closures
10. Classes
11. StdLib (print and clock)
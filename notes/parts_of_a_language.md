# Parts of a language

Let us take the following example.
```
var average = (min + max) / 2
```

## Steps
1. Scanning/Lexing: Takes in a linear stream of characters and chunks them together into "words". The words are called __tokens__. Some tokens are single characters, such as ',' and some are several characters like numbers, string literals, and identifers. 
- For the given example the lexer will output "var" "average" "=" "(" "min" "+" "max" ")" "/" "2" ";", where item in quotes represents tokens.
2. Parsing: Where we define the grammar of the language. Generally built into parse trees or abstract syntax trees.
![Crafting Interpreters tree syntax](../assets/tree.png)
- Parser lets the user know when there are syntax errors.
3. Static analysis: We need to start to define things. For example, in a + b, we know we are adding a and b, but what are they? What is the scope? Where are they defined?
- Step 1 in this is generally __binding__ or __resolution__. So for each indetifier, we match the indentifer to its definition. This is also where type checking generally occurs.
4. Itermediate Represention: The code in the middle that isn't tightly tied to the source or destination. Acts as the interface between them. If you wanted to compile lox into C or Python or whatever, you would start from the IR.
- Generally __one__ front end to generate IR and __one__ back end for each target architecture.
5. Optimizations: Make improvements, but in this case swap out one program with the _same semantics_ but implementing it more efficiently.
- An example is constant folding which is if some expression always evaluates to the same value, then do evaluation at compile time.
```
pennyArea = 3.14159 * (0.75 / 2) * (0.75 / 2);
```
would turn into 
```
pennyArea = 0.4417860938;
```
6. Code generation: Generating the machine code. This can be native code, but also __bytecode__.
7. Runtime: Let the OS load the exectuable.

## Some good to know things
1. Single pass compilers: Parsing, analysis and code gen are interleaved, essentially outputting code directly without allocating syntax trees or IR. 
- Restricts language design
2. Tree-walk interpreters: Interpreter traverses the syntax tree one branch andl eaf at a time.
- Generally slow
3. Transpilers: Compiling frontend into another source as the IR, and then using its compiler to interpreter to finish the lower level semantics.
4. Just-in-time compilation: Take source (interpreted language) and compile it to native code for the supported architecture of the computer.
5. Compiling is translating from one source to another, while interpreting is from source and executes.


## What is being built
1. Tree-walk interpreter of lox
2. Bytecode interpreter running in our own vm

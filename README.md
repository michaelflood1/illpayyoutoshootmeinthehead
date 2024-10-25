# webdev midterm last one im gonna kill myself holy shit

- [Fundamentals](#fundamentals)
    - [ECMAScript](#ecmascript)
    - [Command Line Interface (CLI)](#command-line-interface-cli)
    - [Console](#console)
    - [What's a Path](#whats-a-path)
    - [Absolute vs Relative](#absolute-vs-relative)
    - [Compiler/Interpreted Language](#compiler-interpreted-language)
    - [Runtime Environment vs Interpreter/Compiler](#runtime-environment-vs-interpretercompiler)
    - [JavaScript Program](#js-program)
    - [Asynchronous vs Synchronous](#asynch-vs-synch)
    - [Commands](#commands)
    - [Expressions](#expressions)
    - [Operands](#operands)
    - [Types](#types)
    - [Boolean](#boolean)
    - [Node.js](#nodejs)
    - [Variable Naming](#variable-naming)
    - [Variable Assignment](#variable-assignment)
    - [Keywords](#keywords)
    - [Null Use Cases](#null-usecases)
    - [Order of Operations](#order-f-operations)
    - [Comments](#comments)
    - [Functions](#functions)
    - [Syntax](#syntax)
- [Methods](#methods)
    - [Insertion, Deletion, Iterating Methods](#insertion-deletion-iterating-methods)
    - [String Methods](#string-methods)
    - [Object Methods](#object-methods)
    - [Node-Specific Methods](#node-specific-methods)
    - [Array Methods](#array-methods)
- [Escape Characters](#escape-characters)
- [Mutable vs Immutable](#mutable-immutable)
- [Readline Sync](#readline-sync)
- [Scope](#scope)
- [Conditional Statements](#conditional-statements)
    - [Switch Statement](#switch-statement)
    - [While Loop](#while-loop)
    - [If Statements](#if-statements)
- [Async Callbacks](#async-callbacks)
- [Promises](#promises)
    - [.then/catch vs async](#then-catch-vs-async)
    - [Promise Creation](#promise-creation)
    - [Arman Promise Notes](#arman-promise-notes)
    - [If Error to Promise](#if-err-to-promise)
- [Labs](#labs)
    - [Teacher Code Example](#teacher-code-example)
    - [Word Position Lab](#word-position-lab)
    - [Lab 2: Math Helpers](#lab-2-math-helpers)
    - [Lab 3: argv Web Exports](#lab-3-argv-web-exports)
    - [Lab 4: Generated Answer](#lab-4-generated-answer)
    - [Lab 5: Generated Possible Answer](#lab-5-generated-possible-answer)
    - [Practice Question Possible Answer](#practice-question-possible-answer)

## fundamentals
### ecmascrip
| Feature                   | Description                                                                                                      |
|---------------------------|------------------------------------------------------------------------------------------------------------------|
| **Definition**            | ECMAScript is a standardized scripting language specification that forms the basis for JavaScript.               |
| **Standardization**       | Managed by ECMA International; the first edition was published in 1997.                                         |
| **Versions**              | - **ES1**: 1997 (First Edition)  <br> - **ES2**: 1998  <br> - **ES3**: 1999 (Introduced regular expressions, try/catch) <br> - **ES4**: Abandoned  <br> - **ES5**: 2009 (Added JSON support, strict mode) <br> - **ES6/ES2015**: 2015 (Introduced classes, modules, arrow functions, promises) <br> - **ES7/ES2016**: 2016 (Added Array.prototype.includes, exponentiation operator) <br> - **ES8/ES2017**: 2017 (Added async/await, Object.entries, Object.values) <br> - **ES9/ES2018**: 2018 (Added rest/spread properties, asynchronous iteration) <br> - **ES10/ES2019**: 2019 (Added Array.prototype.flat, Object.fromEntries) <br> - **ES11/ES2020**: 2020 (Added nullish coalescing operator, optional chaining) <br> - **ES12/ES2021**: 2021 (Added logical assignment operators, Promise.any) <br> - **ES13/ES2022**: 2022 (Added class fields, top-level await) |
| **Key Features**          | - **Syntax Improvements**: Simplified syntax for writing JavaScript. <br> - **Modules**: Native support for modules, allowing better code organization. <br> - **Arrow Functions**: Shorter syntax for function expressions. <br> - **Promises and Async/Await**: Improved handling of asynchronous operations. <br> - **Spread and Rest Operators**: Simplified array and object manipulations. |
| **Data Types**            | - **Primitive Types**: Number, String, Boolean, Null, Undefined, Symbol, BigInt. <br> - **Reference Types**: Objects, Arrays, Functions. |
| **Environment**           | Implemented in web browsers, Node.js, and other environments; follows the ECMAScript specification.               |
| **Compatibility**         | Generally backward-compatible, allowing older code to run in newer environments with few issues.                |
| **Popular Implementations**| - **V8**: Chrome and Node.js <br> - **SpiderMonkey**: Firefox <br> - **JavaScriptCore**: Safari                    |


### command line interface cli
- travel through file systems
- used to start Node.js prompt
- only type one statement at a time
- use a text editor or integrated dev envioronment if you need to use a collection of statements

### console
- commandprompt, Terminal
- interact by using keywords (commands)
- text base interface to os

• Clear the terminal screen:
• Windows: cls
• macOS and Unix: clear

• Print the name of the current directory aka folder:
    • Windows: cd (stands for current directory)
    • macOS and Unix: pwd (stands for print working directory)

• Make a new directory:
    • Windows:mkdir name_of_directory
    • macOS and Unit mkdir name_of_directory

• Print a list of environment variables:
    • Windows: set
    • macOS and Unix: env

•Print the value of a specific variable:
    • Windows: set variable_name
    • macOS and Unix: echo $variable_name

• Print information about the system:
    • Windows:    sysinfo (great info!)
    • macOS and Unix:uname –a (a bit anemic)

• Delete a file:
    • Windows:del file_name
    • macOS and Unix: rm file_name

• Delete a directory and all directories and files inside it:
    • Windows:rd /s /q directory_name
    • macOS and Unix: rm –r directory_name

### whats a path
- specifies unique location in file system
- expressed as hierarchy of directories seperated by a delimiting character: / \

#### absolute vs relative
|  absolute | relative    |
|  :-- |  :-- |
|  points to same location always |  starts from current working dir   |
| cd /home/user/exams   | cd exams  |

### compiler/ interpreted language
- compilers take codes humans can read/write and makes it machine useable
- interpreted languages are run line by line
- Node.js runtime reads each line and interprets in real time
 - lexer,parser,compiler creates js bytecode and runtime interpreter turns it into cpu language
### runtime environment vs interpreter/compiler
| Feature               | Runtime Environment                       | Interpreter                               | Compiler                                   |
|-----------------------|------------------------------------------|------------------------------------------|--------------------------------------------|
| **Definition**        | A runtime environment manages the execution of programs. | A program that translates high-level code to machine code line-by-line. | A program that translates the entire high-level code to machine code before execution. |
| **Execution Model**   | Executes programs directly, often providing libraries and services. | Executes code line-by-line, translating and running simultaneously. | Translates the entire code first, then executes the compiled program. |
| **Performance**       | Generally offers higher performance due to optimizations. | Slower execution as each line is interpreted at runtime. | Faster execution once compiled, as the code is already in machine language. |
| **Error Handling**    | Errors are handled during execution, often with runtime checks. | Errors are reported immediately when encountered during interpretation. | Errors are reported after compilation, requiring the entire program to be recompiled for fixes. |
| **Portability**       | May vary between environments, requiring adjustments for different systems. | Typically portable across platforms, provided an interpreter is available. | Often less portable; compiled code may need recompilation for different platforms. |
| **Memory Usage**      | Can consume more memory due to overhead and runtime services. | Generally requires less memory than compiled code, but still needs the interpreter. | Typically uses less memory at runtime as the compiled code is executed directly. |
| **Development Speed** | Allows rapid development and testing cycles, especially for dynamic languages. | Facilitates quick testing and debugging of code snippets. | Slower development cycle due to the need for recompilation after changes. |
| **Examples**          | Java Virtual Machine (JVM), .NET Common Language Runtime (CLR) | Python Interpreter, Ruby MRI, PHP | C, C++, Rust (using standard compilers like GCC, Clang) |
| **Node**              | Node.js is a runtime environment for executing JavaScript server-side, allowing for event-driven, non-blocking I/O. | JavaScript is interpreted in Node.js, executing code directly without prior compilation. | JavaScript code can be compiled using tools like Babel for compatibility but is primarily run in interpreted form in Node.js. |

 ### JS program
 called a script

 sequence of definitions and commands
These are evaluated and the commands are executed one at a
time in order by the JavaScript interpreter
• When we use the Node.js REPL we:
• enter one command
• the JavaScript interpreter executes the command
• Node.js prints the result
• Node.js waits for our next instruction.

### asynch vs synch
| Feature                  | Synchronous Code                                     | Asynchronous Code                                   |
|--------------------------|-----------------------------------------------------|-----------------------------------------------------|
| **Definition**           | Code execution occurs in a sequential manner; each operation must complete before the next begins. | Code execution allows multiple operations to occur concurrently; some operations can be initiated and the program continues running without waiting for them to complete. |
| **Execution Flow**       | Blocking; each function call must finish before the next one starts. | Non-blocking; functions can initiate tasks and return immediately, allowing other code to run. |
| **Performance**          | Can lead to performance bottlenecks, especially during I/O operations (e.g., reading files, network requests). | Can improve performance and responsiveness, particularly in I/O-bound applications. |
| **Error Handling**       | Errors are caught in a straightforward manner using traditional try/catch blocks. | Error handling can be more complex; often uses promises or async/await with try/catch for handling exceptions. |
| **Readability**          | Easier to read and understand due to the linear flow of execution. | Can be harder to read due to nested callbacks (callback hell), but modern syntax (e.g., async/await) improves clarity. |
| **Use Cases**            | Suitable for tasks that require immediate completion, such as calculations or synchronous file reads. | Ideal for I/O-bound tasks like web requests, database operations, or reading/writing files without freezing the application. |
| **Example**              | ```javascript                               <br> function syncFunction() {             <br>   const result = blockingTask();        <br>   console.log(result);                    <br> }                                        <br> syncFunction();``` | ```javascript                                <br> async function asyncFunction() {       <br>   const result = await nonBlockingTask(); <br>   console.log(result);                   <br> }                                        <br> asyncFunction();``` |
| **State Management**     | State is simpler to manage as everything is executed in order. | State management can be more challenging due to the asynchronous nature; can require careful handling of timing and order of operations. |



### commands

Code is the textual representation of a program

Programming is sometimes called coding
A line is a row of text

A command is often called a statement

A command (statement) is a program instruction:

Instructs the interpreter to do something

Programs usually consist of a series of

 Commands end in ; (that’s a semi-colon)

    console.log("This is a random message");
    console.log("Arrested ' + 'development");

### expressions

sequence of operators and operands
sequence specifies a computation
evaluating an expression produce a result
evaluating an expression **may** generate a side affect i.e printing a line to console

### operands

 | **Category**      | **Operator** | **Description**                      | **Example**            | **Result**            |
|-------------------|--------------|--------------------------------------|------------------------|-----------------------|
| **Arithmetic**    | `+`          | Addition                            | `5 + 3`                | `8`                   |
|                   | `-`          | Subtraction                         | `5 - 3`                | `2`                   |
|                   | `*`          | Multiplication                      | `5 * 3`                | `15`                  |
|                   | `/`          | Division                            | `5 / 2`                | `2.5`                 |
|                   | `%`          | Modulus (Remainder)                 | `5 % 2`                | `1`                   |
|                   | `**`         | Exponentiation                      | `2 ** 3`               | `8`                   |
|                   | `++`         | Increment                           | `let a = 1; a++`       | `2`                   |
|                   | `--`         | Decrement                           | `let a = 1; a--`       | `0`                   |
| **Comparison**    | `==`         | Equal to                            | `5 == '5'`             | `true`                |
|                   | `===`        | Strict equal to                     | `5 === '5'`            | `false`               |
|                   | `!=`         | Not equal to                        | `5 != '5'`             | `false`               |
|                   | `!==`        | Strict not equal to                 | `5 !== '5'`            | `true`                |
|                   | `>`          | Greater than                        | `5 > 3`                | `true`                |
|                   | `<`          | Less than                           | `5 < 3`                | `false`               |
|                   | `>=`         | Greater than or equal to            | `5 >= 5`               | `true`                |
|                   | `<=`         | Less than or equal to               | `5 <= 3`               | `false`               |
| **Logical**       | `&&`         | Logical AND                         | `true && false`        | `false`               |
|                   | `||`         | Logical OR                          | `true || false`        | `true`                |
|                   | `!`          | Logical NOT                         | `!true`                | `false`               |
| **Bitwise**       | `&`          | AND                                 | `5 & 1`                | `1`                   |
|                   | `|`          | OR                                  | `5 | 1`                | `5`                   |
|                   | `^`          | XOR                                 | `5 ^ 1`                | `4`                   |
|                   | `~`          | NOT                                 | `~5`                   | `-6`                  |
|                   | `<<`         | Left shift                          | `5 << 1`               | `10`                  |
|                   | `>>`         | Right shift                         | `5 >> 1`               | `2`                   |
|                   | `>>>`        | Zero-fill right shift               | `5 >>> 1`              | `2`                   |
| **Assignment**    | `=`          | Assign                              | `x = 5`                | `x = 5`               |
|                   | `+=`         | Add and assign                      | `x += 5`               | `x = x + 5`           |
|                   | `-=`         | Subtract and assign                 | `x -= 5`               | `x = x - 5`           |
|                   | `*=`         | Multiply and assign                 | `x *= 5`               | `x = x * 5`           |
|                   | `/=`         | Divide and assign                   | `x /= 5`               | `x = x / 5`           |
|                   | `%=`         | Modulus and assign                  | `x %= 2`               | `x = x % 2`           |
|                   | `**=`        | Exponentiation and assign           | `x **= 2`              | `x = x ** 2`          |
|                   | `<<=`        | Left shift and assign               | `x <<= 1`              | `x = x << 1`          |
|                   | `>>=`        | Right shift and assign              | `x >>= 1`              | `x = x >> 1`          |
|                   | `&=`         | AND and assign                      | `x &= 1`               | `x = x & 1`           |
|                   | `|=`         | OR and assign                       | `x |= 1`               | `x = x | 1`           |
|                   | `^=`         | XOR and assign                      | `x ^= 1`               | `x = x ^ 1`           |
| **Ternary**       | `? :`        | Conditional                         | `x > 5 ? 'Yes' : 'No'` | `'Yes'` or `'No'`     |
| **Type**          | `typeof`     | Returns type of operand             | `typeof 42`            | `'number'`            |
|                   | `instanceof` | Checks if an object is an instance  | `obj instanceof Date`  | `true` or `false`     |
| **Spread/Rest**   | `...`        | Spread or rest operator             | `[...arr1, ...arr2]`   | Combined array        |
   
 

### expressions
combination of operators and operands
generate values
values are the core thing js manipulates
every piece of data has a type that defines what we do with it

### types

| **Category**         | **Type**        | **Description**                               | **Example**            | **Result**                  |
|----------------------|-----------------|-----------------------------------------------|------------------------|-----------------------------|
| **Primitive**        | `number`        | Represents numeric values (integers, floats) | `let x = 42;`          | `typeof x // 'number'`      |
|                      | `bigint`        | Represents large integers                    | `let y = 123n;`        | `typeof y // 'bigint'`      |
|                      | `string`        | Represents textual data                      | `let s = 'Hello';`     | `typeof s // 'string'`      |
|                      | `boolean`       | Represents true/false values                 | `let b = true;`        | `typeof b // 'boolean'`     |
|                      | `undefined`     | Denotes an uninitialized variable            | `let u;`               | `typeof u // 'undefined'`   |
|                      | `null`          | Represents intentional absence of value     | `let n = null;`        | `typeof n // 'object'`*     |
|                      | `symbol`        | Unique, immutable identifiers                | `let sym = Symbol();`  | `typeof sym // 'symbol'`    |
| **Non-Primitive**    | `object`        | Collection of key-value pairs                | `let obj = { a: 1 };`  | `typeof obj // 'object'`    |
|                      | `array`         | Ordered list of values                       | `let arr = [1, 2];`    | `typeof arr // 'object'`    |
|                      | `function`      | Executable block of code                     | `function fn() {}`     | `typeof fn // 'function'`   |
| **Built-in Objects** | `Date`          | Represents dates and times                   | `let d = new Date();`  | `d instanceof Date // true` |
|                      | `RegExp`        | Regular expressions for pattern matching     | `/abc/.test('abc')`    | `true`                      |
|                      | `Error`         | Represents runtime errors                    | `new Error('Oops!');`  | `Error: Oops!`              |
|                      | `Promise`       | Represents asynchronous operations           | `Promise.resolve(42);` | Resolves to `42`            |
| **Special Types**    | `NaN`           | Not a number                                 | `0 / 0`                | `NaN`                       |
|                      | `Infinity`      | Represents positive infinity                 | `1 / 0`                | `Infinity`                  |
|                      | `-Infinity`     | Represents negative infinity                 | `-1 / 0`               | `-Infinity`                 |
| **Type Casting**     | `typeof`        | Returns the type of a variable               | `typeof 42`            | `'number'`                  |
|                      | `instanceof`    | Checks if an object is an instance of a type | `[] instanceof Array`  | `true`                      |
| **Special Notes**    | `typeof null`   | Returns `'object'` (legacy quirk)            | `typeof null`          | `'object'`                  |
|                      | `typeof NaN`    | Returns `'number'`                           | `typeof NaN`           | `'number'`                  |

typeof()

### boolean 
true false flags
things that can only have two states are considered truthy/falsy



### Node.js
- REPL: Read evaluate print loop

- enter node in terminal to start Node.js REPL

    node filename.js

### variable naming
| **Rule**                          | **Description**                                          | **Example**                | **Anti-Example**         |
|------------------------------------|----------------------------------------------------------|----------------------------|--------------------------|
| **Use meaningful names**           | Name variables based on their purpose or content         | `let userAge = 25;`        | `let x = 25;`            |
| **CamelCase for variables**        | Start with lowercase, capitalize subsequent words        | `let firstName = 'John';`  | `let Firstname = 'John';`|
| **Avoid single letters (unless loop variables)** | Single letters are confusing except in loops | `for (let i = 0; i < n; i++)` | `let a = 10;` |
| **Be descriptive but concise**     | Keep names short but understandable                      | `let maxAttempts = 5;`     | `let m = 5;`             |
| **Use nouns for variables**        | Variables represent data, so prefer nouns                | `let userCount = 10;`      | `let countUsers = 10;`   |
| **Prefix Booleans with 'is', 'has', or 'can'** | Clarifies intent of Boolean variables            | `let isLoggedIn = true;`   | `let loggedIn = true;`   |
| **Use plural for arrays**          | Indicate collections by using plural names               | `let users = ['Alice'];`   | `let user = ['Alice'];`  |
| **Avoid abbreviations**            | Use full words for clarity                               | `let totalAmount = 100;`   | `let amt = 100;`         |
| **Avoid reserved words**           | Don’t use JavaScript keywords as variable names          | `let userClass = 'A';`     | `let class = 'A';`       |
| **Use constants in UPPER_SNAKE_CASE** | Signals that the value shouldn’t change               | `const MAX_LIMIT = 100;`   | `const maxLimit = 100;`  |
| **Indicate units where relevant**  | Helps clarify what the value represents                  | `let fileSizeKB = 500;`    | `let fileSize = 500;`    |
| **Avoid magic numbers**            | Use variables/constants instead of hard-coded values     | `const RETRY_COUNT = 3;`   | `if (x === 3) {...}`     |

### variable assignment

| **Keyword** | **Use Case**                      | **Scope**                | **Behavior**                                      | **Example**                |
|-------------|------------------------------------|--------------------------|--------------------------------------------------|----------------------------|
| `const`     | For values that won’t change      | Block-scoped             | Must be initialized during declaration; value cannot be reassigned | `const PI = 3.14159;`      |
| `let`       | For values that will change       | Block-scoped             | Can be reassigned; cannot be redeclared within the same scope | `let counter = 0;`         |
| `var`       | Avoid using (legacy behavior)     | Function-scoped or global | Can be redeclared and reassigned; hoisted but with undefined value before initialization | `var name = 'Alice';`      |

var is bad because the value doesnt respect block scope and undefined until assigned

### keywords

| **Category**         | **Keyword**       | **Description**                                     | **Example**                       |
|----------------------|-------------------|-----------------------------------------------------|-----------------------------------|
| **Declarations**     | `var`             | Declares a variable (function-scoped)               | `var name = 'Alice';`            |
|                      | `let`             | Declares a block-scoped variable                    | `let age = 30;`                  |
|                      | `const`           | Declares a constant (block-scoped)                  | `const PI = 3.14;`               |
| **Functions & Classes** | `function`    | Declares a function                                 | `function greet() {}`            |
|                      | `class`           | Declares a class                                    | `class User {}`                  |
|                      | `extends`         | Inherits a class                                    | `class Admin extends User {}`    |
|                      | `constructor`     | Declares a class constructor                        | `constructor(name) {}`           |
| **Control Flow**     | `if`              | Starts an `if` conditional block                    | `if (x > 5) {}`                  |
|                      | `else`            | Defines an alternate block                          | `else {}`                        |
|                      | `switch`          | Starts a switch statement                           | `switch (value) {}`              |
|                      | `case`            | Defines a case inside a switch                      | `case 1:`                        |
|                      | `default`         | Default case in switch                              | `default:`                       |
|                      | `for`             | Declares a for loop                                 | `for (let i = 0; i < 5; i++)`    |
|                      | `while`           | Declares a while loop                               | `while (x < 5) {}`               |
|                      | `do`              | Starts a do-while loop                              | `do { } while (x < 5);`          |
|                      | `break`           | Exits from a loop or switch                         | `break;`                         |
|                      | `continue`        | Skips current iteration of a loop                   | `continue;`                      |
| **Error Handling**   | `try`             | Starts a try block                                  | `try { }`                        |
|                      | `catch`           | Catches errors from try block                       | `catch (e) {}`                   |
|                      | `finally`         | Executes after try-catch                            | `finally {}`                     |
|                      | `throw`           | Throws an exception                                 | `throw new Error('Oops!');`      |
| **Asynchronous**     | `async`           | Declares an asynchronous function                   | `async function fetchData() {}`  |
|                      | `await`           | Waits for a promise to resolve                      | `await fetch(url);`              |
| **Object Handling**  | `this`            | Refers to the current object                        | `this.name = 'Alice';`           |
|                      | `new`             | Creates an instance of an object or class           | `new Date();`                    |
|                      | `delete`          | Deletes a property from an object                   | `delete obj.key;`                |
|                      | `typeof`          | Returns the type of a value                         | `typeof x;`                      |
|                      | `instanceof`      | Checks if an object is an instance of a class       | `obj instanceof Array;`          |
| **Modules & Import** | `import`          | Imports modules or dependencies                     | `import fs from 'fs';`           |
|                      | `export`          | Exports modules or variables                        | `export const x = 5;`            |
|                      | `require`         | Imports modules (CommonJS)                          | `const fs = require('fs');`      |
|                      | `module`          | References the current module                       | `module.exports = {}`            |
| **Keywords for Iterators** | `yield`     | Pauses and resumes a generator function             | `yield value;`                   |
|                      | `return`          | Returns a value from a function                     | `return 5;`                      |
| **Constants**        | `true`            | Boolean value                                       | `let isActive = true;`           |
|                      | `false`           | Boolean value                                       | `let isActive = false;`          |
|                      | `null`            | Represents an intentional absence of value         | `let user = null;`               |
|                      | `undefined`       | Represents an uninitialized value                  | `let x; // undefined`            |
| **Loops & Iterators**| `in`              | Iterates over object properties                     | `for (key in obj) {}`            |
|                      | `of`              | Iterates over iterable objects                      | `for (value of arr) {}`          |
| **Reserved Future**  | `super`           | Calls parent class constructor                     | `super(name);`                   |
|                      | `with`            | Deprecated, avoid using                            | `with (obj) {}`                  |
|                      | `debugger`        | Pauses execution for debugging                     | `debugger;`                      |

### null usecases
| **Use Case**                    | **Description**                                        | **Example**                                |
|----------------------------------|--------------------------------------------------------|--------------------------------------------|
| **Intentional absence of value** | Use `null` to show that a value is explicitly empty    | `let user = null;`                        |
| **Resetting variables**          | Assign `null` to clear a variable’s value              | `let result = null;`                      |
| **Initialization before async data** | Initialize variables that will later hold fetched data | `let data = null;`                        |
| **Checking for uninitialized state** | Differentiate between uninitialized (`undefined`) and empty (`null`) state | `if (user === null) { ... }` |
| **Placeholder for optional objects** | Use `null` for properties that may or may not hold objects | `let settings = { theme: null };` |
| **Indicating failure or invalid result** | Assign `null` to represent invalid data in some operations | `let value = getValue() || null;`        |


### Order f operations

| **Operation**       | **Operator**        | **Example**                      | **Precedence (High → Low)** |
|---------------------|---------------------|----------------------------------|-----------------------------|
| **Parentheses**     | `()`                | `(2 + 3) * 4` = 20              | 1                           |
| **Exponentiation**  | `**`                | `2 ** 3` = 8                    | 2                           |
| **Multiplication**  | `*`                 | `2 * 3` = 6                     | 3                           |
| **Division**        | `/`                 | `6 / 2` = 3                     | 3                           |
| **Modulo (Remainder)** | `%`              | `5 % 2` = 1                     | 3                           |
| **Addition**        | `+`                 | `2 + 3` = 5                     | 4                           |
| **Subtraction**     | `-`                 | `5 - 2` = 3                     | 4                           |
| **Left-to-Right Evaluation** | (for same precedence) | `10 / 2 * 3` = 15 | N/A                         |



### comments
enable readable code
ignored by interpreter
every js file u create should have comments at the top

    // im a comment i describe code

    /*
     im a long comment im more descriptive
     */

### functions
use by invoking name
some functions return a value
can call other functions


consists of
- ketword function
- new functions name followed by parentheses and open curly
- indented block of statements
- closed curly

    function_greet() {
        console.log("do not get discord hacked like hitarth");
    }

```javascript

// Basic Greeting Function
function greetUser(name) {
  // If no name is provided, use 'Guest' as the default value
  if (!name) {
    name = 'Guest';
  }
  
  // Construct a greeting message
  return `Hello, ${name}! Welcome to our platform.`;
}

// Example usage
console.log(greetUser('Alice')); // Output: Hello, Alice! Welcome to our platform.
console.log(greetUser());        // Output: Hello, Guest! Welcome to our platform.


const fs = require('fs');

// Asynchronous File Reader Function
function readFileAsync(filePath) {
  // Use fs.readFile to read the file asynchronously
  fs.readFile(filePath, 'utf8', (err, data) => {
    // Handle any error that occurs during the reading process
    if (err) {
      console.error('Error reading file:', err);
      return;
    }

    // Log the content of the file to the console
    console.log('File Content:\n', data);
  });
}

// Example usage
readFileAsync('./example.txt'); // Ensure this file exists in the same directory

const https = require('https');

// Asynchronous function to fetch data from an API
function fetchDataFromAPI(url) {
  return new Promise((resolve, reject) => {
    // Make an HTTPS GET request to the provided URL
    https.get(url, (response) => {
      let data = '';

      // Accumulate data chunks as they arrive
      response.on('data', (chunk) => {
        data += chunk;
      });

      // When all data has been received, resolve the promise
      response.on('end', () => {
        try {
          // Parse the JSON response and resolve the promise with the result
          const jsonData = JSON.parse(data);
          resolve(jsonData);
        } catch (error) {
          // If parsing fails, reject the promise with an error
          reject(new Error('Failed to parse JSON response.'));
        }
      });

    }).on('error', (err) => {
      // If an error occurs during the request, reject the promise
      reject(err);
    });
  });
}

// Example usage with async/await
(async () => {
  try {
    const apiUrl = 'https://jsonplaceholder.typicode.com/todos/1';
    const data = await fetchDataFromAPI(apiUrl);
    console.log('API Data:', data);
  } catch (error) {
    console.error('Error fetching data:', error.message);
  }
})();
```

### .syntax
Dot syntax (or dot notation) is a way to access properties and methods of an object in JavaScript (and by extension, Node.js). It uses a dot (.) followed by the property or method name to reference or call the desired item. This syntax is common in object-oriented programming and is widely used for interacting with objects in JavaScript.

    const car = {
        make: 'Toyota',
        model: 'Camry',
        year: 2020,
     };

    console.log(car.make); // Output: Toyota
    console.log(car.model); // Output: Camry

    const person = {
     'age years': 30,
    };

    console.log(person['age years']); // Output: 30
## methods
### insertion deletion iterating methods
| Operation  | Method/Function                  | Description                                      | Example Output                          |
|------------|----------------------------------|--------------------------------------------------|-----------------------------------------|
| Inserting  | `list.append(item)`             | Adds an item to the end of the list.            | `list = [1, 2, 3]; list.append(4)` -> `[1, 2, 3, 4]` |
|            | `list.insert(index, item)`      | Inserts an item at a specified index.           | `list.insert(1, 5)` -> `[1, 5, 2, 3, 4]` |
|            | `list.extend(iterable)`          | Extends the list by appending elements from an iterable. | `list.extend([5, 6])` -> `[1, 5, 2, 3, 4, 5, 6]` |
|            | `dict[key] = value`             | Inserts a key-value pair in a dictionary.       | `dict = {}; dict['a'] = 1` -> `{'a': 1}` |
|            | `dict.update({key: value})`     | Updates the dictionary with key-value pairs from another dictionary or an iterable. | `dict.update({'b': 2})` -> `{'a': 1, 'b': 2}` |
|            | `dict.setdefault(key, default)` | Inserts a key with a default value if the key is not already in the dictionary. | `dict.setdefault('c', 3)` -> `{'a': 1, 'b': 2, 'c': 3}` |
|            | `set.add(item)`                 | Adds an item to the set.                         | `set = {1, 2}; set.add(3)` -> `{1, 2, 3}` |
| Deleting   | `list.remove(item)`             | Removes the first occurrence of a specified item. | `list.remove(2)` -> `[1, 5, 3, 4, 5, 6]` |
|            | `list.pop(index)`               | Removes and returns an item at the specified index. | `list.pop(1)` -> `5` (if `list` is `[1, 5, 3, 4, 5, 6]`) |
|            | `del list[index]`               | Deletes an item at the specified index.          | `del list[0]` -> `[5, 3, 4, 5, 6]` |
|            | `dict.pop(key)`                 | Removes a key-value pair and returns the value. | `dict.pop('b')` -> `2` (if `dict` is `{'a': 1, 'b': 2}`) |
|            | `dict.popitem()`                | Removes and returns the last inserted key-value pair. | `dict.popitem()` -> `('c', 3)` (if `dict` is `{'a': 1, 'b': 2, 'c': 3}`) |
|            | `set.remove(item)`              | Removes a specified item from the set. Raises KeyError if not found. | `set.remove(2)` -> `{1, 3}` |
| Iterating  | `for item in list:`             | Iterates over each item in the list.             | `for item in [1, 2, 3]: print(item)` -> `1\n2\n3` |
|            | `for key in dict:`              | Iterates over each key in the dictionary.        | `for key in {'a': 1, 'b': 2}: print(key)` -> `a\nb` |
|            | `for item in set:`              | Iterates over each item in the set.              | `for item in {1, 2, 3}: print(item)` -> `1\n2\n3` (order may vary) |
|            | `enumerate(list):`              | Returns both index and item for each iteration.  | `for index, item in enumerate([1, 2, 3]): print(index, item)` -> `0 1\n1 2\n2 3` |
|            | `dict.keys()`                   | Returns a view object displaying a list of all keys in the dictionary. | `dict.keys()` -> `dict_keys(['a', 'b'])` |
|            | `dict.values()`                 | Returns a view object displaying a list of all values in the dictionary. | `dict.values()` -> `dict_values([1, 2])` |
|            | `dict.items()`                  | Returns a view object displaying a list of key-value tuple pairs. | `dict.items()` -> `dict_items([('a', 1), ('b', 2)])` |
|            | `dict.items()` with unpacking   | Iterates over key-value pairs, allowing unpacking. | `for key, value in dict.items(): print(key, value)` -> `a 1\nb 2` |

### string methods
| **Method**                     | **Description**                                                | **Example**                                        | **Example Output**             |
|--------------------------------|---------------------------------------------------------------|----------------------------------------------------|---------------------------------|
| `charAt(index)`               | Returns the character at the specified index.                | `'hello'.charAt(1)`                               | `e`                             |
| `concat(string1, string2, ...)`| Combines two or more strings and returns a new string.       | `'Hello'.concat(' ', 'World!')`                  | `Hello World!`                 |
| `includes(searchString)`      | Determines whether a string contains a specified substring.   | `'Hello World'.includes('World')`                 | `true`                          |
| `indexOf(searchValue)`        | Returns the index of the first occurrence of a specified value. | `'Hello World'.indexOf('o')`                    | `4`                             |
| `lastIndexOf(searchValue)`    | Returns the index of the last occurrence of a specified value. | `'Hello World'.lastIndexOf('o')`                | `7`                             |
| `length`                      | Returns the length of the string.                             | `'Hello'.length`                                  | `5`                             |
| `replace(searchValue, newValue)` | Returns a new string with some or all matches of a pattern replaced by a replacement. | `'Hello World'.replace('World', 'JavaScript')` | `Hello JavaScript`             |
| `slice(start, end)`           | Extracts a section of a string and returns it as a new string. | `'Hello World'.slice(0, 5)`                     | `Hello`                        |
| `split(separator)`            | Splits a string into an array of substrings based on a specified separator. | `'a,b,c'.split(',')`                           | `['a', 'b', 'c']`              |
| `substring(start, end)`       | Returns a portion of the string between two specified indices. | `'Hello World'.substring(0, 5)`                 | `Hello`                        |
| `toLowerCase()`               | Returns the string with all characters converted to lowercase. | `'Hello'.toLowerCase()`                          | `hello`                        |
| `toUpperCase()`               | Returns the string with all characters converted to uppercase. | `'Hello'.toUpperCase()`                          | `HELLO`                        |
| `trim()`                      | Removes whitespace from both ends of a string.                | `'   Hello World   '.trim()`                     | `Hello World`                  |

### object methods
| **Method**                   | **Description**                                         | **Example**                              |
|------------------------------|---------------------------------------------------------|------------------------------------------|
| `Object.keys(obj)`           | Returns an array of a given object's own property names. | `Object.keys({ a: 1, b: 2 })` → `['a', 'b']` |
| `Object.values(obj)`         | Returns an array of a given object's own property values. | `Object.values({ a: 1, b: 2 })` → `[1, 2]` |
| `Object.entries(obj)`        | Returns an array of a given object's own enumerable string-keyed property [key, value] pairs. | `Object.entries({ a: 1, b: 2 })` → `[['a', 1], ['b', 2]]` |
| `Object.assign(target, ...sources)` | Copies values of all enumerable properties from one or more source objects to a target object. | `Object.assign({}, { a: 1 }, { b: 2 })` → `{ a: 1, b: 2 }` |
| `Object.freeze(obj)`        | Freezes an object, preventing new properties from being added and existing properties from being removed or altered. | `const obj = Object.freeze({ a: 1 });` |
| `Object.seal(obj)`          | Seals an object, preventing new properties from being added but allowing existing properties to be modified. | `const obj = Object.seal({ a: 1 });` |
| `Object.hasOwn(obj, prop)`  | Returns a boolean indicating whether an object has the specified property as its own property. | `Object.hasOwn(obj, 'a')` → `true` |

### NODE SPECIFIC METHODS
| **Item**                    | **Description**                                          | **Example**                             |
|-----------------------------|----------------------------------------------------------|-----------------------------------------|
| `fs.readFile(path, callback)` | Asynchronously reads the contents of a file.          | `fs.readFile('file.txt', (err, data) => { ... });` |
| `fs.writeFile(path, data, callback)` | Asynchronously writes data to a file, replacing the file if it already exists. | `fs.writeFile('file.txt', 'Hello World', (err) => { ... });` |
| `http.createServer(callback)` | Creates an HTTP server that listens to requests.     | `http.createServer((req, res) => { ... });` |
| `path.join([...paths])`     | Joins all given path segments together using the platform-specific separator. | `path.join('folder', 'file.txt')` → `'folder/file.txt'` (on Unix) |
| `process.env`               | Provides access to environment variables.               | `console.log(process.env.NODE_ENV);`  |
| `Buffer.from(array)`        | Creates a new Buffer containing the octets from the array. | `const buf = Buffer.from([1, 2, 3]);` |
| `setTimeout(callback, delay)` | Calls a function after a specified delay.            | `setTimeout(() => { console.log('Hello'); }, 1000);` |

### array methods
| **Method**                     | **Description**                                          | **Example**                                 |
|--------------------------------|----------------------------------------------------------|---------------------------------------------|
| `Array.isArray(value)`        | Checks if a value is an array.                          | `Array.isArray([1, 2, 3])` → `true`       |
| `push(element)`               | Adds one or more elements to the end of an array.      | `let arr = [1, 2]; arr.push(3);` → `[1, 2, 3]` |
| `pop()`                       | Removes the last element from an array and returns it.  | `arr.pop()` → `3` (for `[1, 2, 3]`)       |
| `shift()`                     | Removes the first element from an array and returns it. | `arr.shift()` → `1` (for `[1, 2, 3]`)     |
| `unshift(element)`            | Adds one or more elements to the beginning of an array. | `arr.unshift(0)` → `[0, 1, 2]`             |
| `concat(...arrays)`           | Merges two or more arrays and returns a new array.      | `[1, 2].concat([3, 4])` → `[1, 2, 3, 4]`  |
| `join(separator)`             | Joins all elements of an array into a string.           | `arr.join(', ')` → `'1, 2, 3'`            |
| `slice(start, end)`           | Returns a shallow copy of a portion of an array.        | `arr.slice(1, 3)` → `[2, 3]`              |
| `splice(start, deleteCount, ...items)` | Changes the contents of an array by removing or replacing existing elements and/or adding new elements. | `arr.splice(1, 1, 4)` → `[1, 4, 3]` (for `[1, 2, 3]`) |
| `forEach(callback)`           | Executes a provided function once for each array element.| `arr.forEach(num => console.log(num));`  |
| `map(callback)`               | Creates a new array populated with the results of calling a provided function on every element in the calling array. | `arr.map(num => num * 2)` → `[2, 4, 6]`   |
| `filter(callback)`            | Creates a new array with all elements that pass the test implemented by the provided function. | `arr.filter(num => num > 1)` → `[2, 3]`   |
| `reduce(callback, initialValue)` | Executes a reducer function on each element of the array, resulting in a single output value. | `arr.reduce((acc, num) => acc + num, 0)` → `6` |
| `find(callback)`              | Returns the value of the first element in the array that satisfies the provided testing function. | `arr.find(num => num > 1)` → `2`          |
| `includes(value)`             | Determines whether an array includes a certain value among its entries. | `arr.includes(2)` → `true`                 |
| `sort(compareFunction)`       | Sorts the elements of an array in place and returns the sorted array. | `arr.sort((a, b) => a - b)` → `[1, 2, 3]` |
| `reverse()`                   | Reverses the elements of an array in place.             | `arr.reverse()` → `[3, 2, 1]`              |
| `flat(depth)`                 | Creates a new array with all sub-array elements concatenated into it recursively up to the specified depth. | `[[1, 2], [3, 4]].flat()` → `[1, 2, 3, 4]` |


### escape characters
| **Escape Character** | **Description**                                        | **Example**                                       | **Example Output**                  |
|-----------------------|--------------------------------------------------------|---------------------------------------------------|-------------------------------------|
| `\'`                  | Single quote                                          | `'It\'s a nice day.'`                             | `It's a nice day.`                  |
| `\"`                  | Double quote                                          | `"He said, \"Hello!\""`                           | `He said, "Hello!"`                 |
| `\\`                  | Backslash                                             | `'This is a backslash: \\'`                       | `This is a backslash: \`            |
| `\n`                  | New line (line break)                                | `'Hello,\nWorld!'`                               | `Hello,` (new line) `World!`       |
| `\r`                  | Carriage return                                       | `'Hello,\rWorld!'`                               | `World!` (overwrites 'Hello,')     |
| `\t`                  | Horizontal tab                                        | `'Hello\tWorld!'`                                | `Hello    World!`                   |
| `\b`                  | Backspace                                             | `'Hello\bWorld!'`                                | `HellWorld!`                        |
| `\f`                  | Form feed                                            | `'Hello\fWorld!'`                                | (may vary; usually not visible)     |
| `\v`                  | Vertical tab                                          | `'Hello\vWorld!'`                                | (may vary; usually not visible)     |
| `\0`                  | Null character                                        | `'Hello\0World!'`                                | `Hello` (string terminates at null) |
| `\uXXXX`             | Unicode escape sequence (4 hexadecimal digits)       | `'\u03A9'`                                       | `Ω` (Greek capital letter Omega)    |
| `\xXX`               | Hexadecimal escape sequence (2 hexadecimal digits)   | `'\x41'`                                         | `A`                                  |

### mutable immutable

| **Data Type**        | **Mutable/Immutable** | **Description**                                                                 |
|----------------------|-----------------------|---------------------------------------------------------------------------------|
| **Object**           | Mutable               | Objects can be modified after creation; properties can be added, changed, or removed. |
| **Array**            | Mutable               | Arrays are a special type of object that can change their elements or length.   |
| **Function**         | Mutable               | Functions are objects and can be modified (e.g., properties can be added).      |
| **String**           | Immutable             | Strings cannot be changed once created; any modification results in a new string. |
| **Number**           | Immutable             | Numbers cannot be modified; any operation creates a new number.                  |
| **Boolean**          | Immutable             | Booleans are immutable; they cannot be changed after creation.                   |
| **Symbol**           | Immutable             | Symbols are unique and immutable; once created, their value cannot be altered.   |
| **BigInt**           | Immutable             | BigInt values cannot be changed after creation; any operation produces a new value. |


### readline sync

    npm install readline-sync

    // Import the readline-sync module
    const readline = require('readline-sync');

    // Prompt the user for their name
    const name = readline.question('What is your name? ');

    // Display a greeting
    console.log(`Hello, ${name}!`);

    // Prompt for a number
    const age = readline.questionInt('How old are you? ');

    // Display the age
    console.log(`You are ${age} years old.`);

### scope 
| **Scope Type**       | **Description**                                                                 | **Example**                                                                                          |
|----------------------|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| **Global Scope**     | Variables declared in the global scope are accessible throughout the entire application. In Node.js, the global object is `global`. | ```javascript globalVar = 'I am global'; console.log(globalVar); // Output: I am global ```          |
| **Function Scope**   | Variables declared within a function are local to that function and cannot be accessed outside of it. | ```javascript function myFunction() { const funcVar = 'I am local'; } myFunction(); console.log(funcVar); // Error: funcVar is not defined ``` |
| **Block Scope**      | Variables declared with `let` and `const` inside a block (e.g., if statements, loops) are limited to that block. | ```javascript if (true) { let blockVar = 'I am in a block'; } console.log(blockVar); // Error: blockVar is not defined ``` |
| **Module Scope**     | In Node.js, each file is treated as a separate module. Variables declared in a module are not accessible outside of that module unless explicitly exported. | ```javascript // In file1.js const moduleVar = 'I am module-scoped'; module.exports = { moduleVar }; // In file2.js const { moduleVar } = require('./file1'); console.log(moduleVar); // Output: I am module-scoped ``` |
## Conditional statements
### switch statement
| **Pattern/Method**          | **Description**                                                                                       | **Example**                                                                                                           |
|-----------------------------|-------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Basic Switch Statement**   | Evaluates an expression and matches it against multiple cases.                                       | ```javascript const fruit = 'apple'; switch (fruit) { case 'apple': console.log('You chose an apple.'); break; case 'banana': console.log('You chose a banana.'); break; default: console.log('Unknown fruit.'); } // Output: You chose an apple. ``` |
| **Fall-through Case**       | Cases without a `break` statement allow execution to fall through to the next case.                  | ```javascript const num = 2; switch (num) { case 1: console.log('One'); case 2: console.log('Two'); case 3: console.log('Three'); break; } // Output: Two ``` |
| **Multiple Cases**          | Multiple case labels can be combined to execute the same block of code for different values.        | ```javascript const day = 'Saturday'; switch (day) { case 'Saturday': case 'Sunday': console.log('It\'s the weekend!'); break; case 'Monday': console.log('Back to work.'); break; } // Output: It's the weekend! ``` |
| **Switch with Expressions** | The expression can be any valid expression, not just a variable.                                     | ```javascript const x = 5; switch (true) { case (x < 10): console.log('x is less than 10.'); break; case (x === 5): console.log('x is equal to 5.'); break; } // Output: x is less than 10. ``` |
| **Default Case**            | The `default` case is executed if no case matches, acting as a fallback.                             | ```javascript const color = 'purple'; switch (color) { case 'red': console.log('Red color'); break; case 'blue': console.log('Blue color'); break; default: console.log('Color not recognized.'); break; } // Output: Color not recognized. ``` |

each case is a potential value for your switch (value)
```javascript

// Define a variable to represent the day of the week
const day = 'Wednesday';

// Use a switch statement to determine the message based on the day
switch (day) {
    case 'Monday':
        console.log('Today is Monday. Start of the work week!');
        break;
    case 'Tuesday':
        console.log('Today is Tuesday. Keep going!');
        break;
    case 'Wednesday':
        console.log('Today is Wednesday. We are halfway through the week!');
        break;
    case 'Thursday':
        console.log('Today is Thursday. Almost there!');
        break;
    case 'Friday':
        console.log('Today is Friday. Weekend is near!');
        break;
    case 'Saturday':
        console.log('Today is Saturday. Enjoy your weekend!');
        break;
    case 'Sunday':
        console.log('Today is Sunday. Prepare for the week ahead!');
        break;
    default:
        console.log('Invalid day. Please enter a valid day of the week.');
        break;
}

// Output: Today is Wednesday. We are halfway through the week!
```

### while loop

| **Method/Pattern**      | **Description**                                                                                 | **Example**                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
| **Basic While Loop**    | Executes a block of code as long as the condition evaluates to true.                          | ```javascript let i = 0; while (i < 5) { console.log(i); i++; } // Output: 0, 1, 2, 3, 4 ```               |
| **Infinite While Loop** | A loop that continues indefinitely unless a `break` statement is used.                        | ```javascript let j = 0; while (true) { console.log(j); j++; if (j > 5) break; } // Output: 0, 1, 2, 3, 4, 5 ``` |
| **While with User Input**| Continuously prompts the user for input until a specific condition is met.                   | ```javascript const readline = require('readline-sync'); let input; while (input !== 'exit') { input = readline.question('Type exit to quit: '); } ``` |
| **While Loop with Condition** | Using complex conditions for the loop to control its execution based on multiple variables. | ```javascript let a = 0, b = 5; while (a < b) { console.log(a); a++; b--; } // Output: 0, 1, 2 ```         |
| **Nested While Loop**   | A `while` loop inside another `while` loop, allowing for multi-dimensional iteration.         | ```javascript let i = 0; while (i < 3) { let j = 0; while (j < 2) { console.log(`i: ${i}, j: ${j}`); j++; } i++; } // Output: i: 0, j: 0, i: 0, j: 1, ... ``` |


```javascript
// Initialize a counter variable
let count = 1;

// Use a while loop to count from 1 to 5
while (count <= 5) {
    console.log(`Count: ${count}`); // Print the current count
    count++; // Increment the counter by 1
}

// Output:
// Count: 1
// Count: 2
// Count: 3
// Count: 4
// Count: 5


// or

// Import the readline-sync module for user input
const readline = require('readline-sync');

// Generate a random number between 1 and 10
const randomNumber = Math.floor(Math.random() * 10) + 1;

let guess; // Initialize the guess variable

console.log('Welcome to the Number Guessing Game!');
console.log('Guess a number between 1 and 10.');

// Start the while loop to prompt the user for guesses
while (guess !== randomNumber) {
    // Prompt the user for their guess
    guess = readline.questionInt('Enter your guess: ');

    // Check if the guess is correct
    if (guess < randomNumber) {
        console.log('Too low! Try again.'); // Provide feedback if the guess is too low
    } else if (guess > randomNumber) {
        console.log('Too high! Try again.'); // Provide feedback if the guess is too high
    } else {
        console.log(`Congratulations! You guessed the number ${randomNumber}!`); // Correct guess
    }
}
//or

const readline = require("readline-sync");
var continueLooping = true;
while (continueLooping === true) {
    // do some stuff
    var user = readline.question("Enter Q to quit: ");
    if (user.toUpperCase() === "Q") {
        continueLooping = false;
    }
}
```

### if statements

| **Pattern/Method**           | **Description**                                                                                       | **Example**                                                                                                            |
|------------------------------|-------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| **Basic If Statement**       | Executes a block of code if the condition evaluates to true.                                        | ```javascript const age = 18; if (age >= 18) { console.log('You are an adult.'); } // Output: You are an adult. ```  |
| **If-Else Statement**        | Provides an alternative block of code that executes if the condition is false.                       | ```javascript const age = 16; if (age >= 18) { console.log('You are an adult.'); } else { console.log('You are a minor.'); } // Output: You are a minor. ``` |
| **If-Else If-Else Statement**| Allows multiple conditions to be checked in sequence.                                               | ```javascript const score = 85; if (score >= 90) { console.log('Grade: A'); } else if (score >= 80) { console.log('Grade: B'); } else { console.log('Grade: C'); } // Output: Grade: B ``` |
| **Nested If Statements**     | An `if` statement inside another `if` statement, allowing for complex conditional checks.            | ```javascript const temp = 30; if (temp > 0) { if (temp < 20) { console.log('It\'s cold.'); } else { console.log('It\'s warm.'); } } // Output: It's warm. ``` |
| **Ternary Operator**         | A shorthand for `if-else` that returns values based on a condition.                                 | ```javascript const isLoggedIn = true; const message = isLoggedIn ? 'Welcome back!' : 'Please log in.'; console.log(message); // Output: Welcome back! ``` |
| **Logical Operators**        | Combines multiple conditions using logical operators (`&&` for AND, `||` for OR).                   | ```javascript const age = 25; const hasID = true; if (age >= 18 && hasID) { console.log('You can enter.'); } // Output: You can enter. ``` |

### if
```javascript
let balance = 1000;

if (balance >= 5000) {
  console.log('You have a high balance! Consider investing.');
} 
else if (balance >= 1000) {
  console.log('Your balance is good. Keep saving!');
} 
else if (balance >= 0) {
  console.log('Your balance is low. Watch your spending.');
} 
else {
  console.log('Your account is overdrawn!');
}



let trafficLight = 'yellow';

if (trafficLight === 'green') {
  console.log('Go!');
} 
else if (trafficLight === 'yellow') {
  console.log('Slow down and prepare to stop.');
} 
else if (trafficLight === 'red') {
  console.log('Stop!');
} 
else {
  console.log('Invalid traffic light signal.');
}



let secretNumber = 7;
let guess = 5;

if (guess === secretNumber) {
  console.log('Congratulations! You guessed the number.');
} 
else if (guess > secretNumber) {
  console.log('Too high! Try a smaller number.');
} 
else if (guess < secretNumber) {
  console.log('Too low! Try a bigger number.');
} 
else {
  console.log('Invalid input.');
}


```
### async callbacks
| **Pattern/Method**               | **Description**                                                                                   | **Example**                                                                                                         |
|----------------------------------|---------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Basic Asynchronous Callback**   | A function passed to another function that executes after a delay or event.                     | ```javascript function fetchData(callback) { setTimeout(() => { callback('Data received'); }, 2000); } fetchData(console.log); // Output after 2 seconds: Data received ``` |
| **Error-First Callback**         | A common convention where the first parameter is reserved for an error, if one occurs.         | ```javascript function readFile(callback) { const error = null; const data = 'File content'; callback(error, data); } readFile((err, data) => { if (err) { console.error(err); } else { console.log(data); } }); // Output: File content ``` |
| **Callback Hell (Pyramid of Doom)** | A situation where callbacks are nested, leading to hard-to-read code.                         | ```javascript asyncFunction1((result1) => { asyncFunction2(result1, (result2) => { asyncFunction3(result2, (result3) => { console.log(result3); }); }); }); // Nested callbacks ``` |
| **Named Callback Function**      | Using a named function instead of an anonymous function for clarity and reusability.           | ```javascript function handleResult(result) { console.log(result); } fetchData(handleResult); // Output after 2 seconds: Data received ``` |
| **Using Promises (to avoid callbacks)** | Promises provide a cleaner alternative to callbacks for handling asynchronous operations.   | ```javascript function fetchData() { return new Promise((resolve) => { setTimeout(() => { resolve('Data received'); }, 2000); }); } fetchData().then(console.log); // Output after 2 seconds: Data received ``` |




### promises
const fs = require("node:fs/promises");

| **Method**                | **Description**                                                                                 | **Parameters**                                                | **Returns**                                   | **Example**                                                                                                          |
|---------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------|-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| `fs.access()`             | Tests a user's permissions for the file or directory.                                         | `path`, `mode` (optional)                                   | `Promise<void>`                               | ```javascript await fs.access('file.txt'); // Checks if file.txt is accessible. ```                                 |
| `fs.appendFile()`         | Appends data to a file, creating the file if it does not exist.                              | `path`, `data`, `options` (optional)                       | `Promise<void>`                               | ```javascript await fs.appendFile('file.txt', 'New data'); // Appends "New data" to file.txt. ```                  |
| `fs.chmod()`              | Changes the permissions of a file or directory.                                              | `path`, `mode`                                              | `Promise<void>`                               | ```javascript await fs.chmod('file.txt', 0o755); // Changes permissions of file.txt to 755. ```                    |
| `fs.copyFile()`          | Copies a file from one location to another.                                                  | `src`, `dest`, `flags` (optional)                          | `Promise<void>`                               | ```javascript await fs.copyFile('source.txt', 'destination.txt'); // Copies source.txt to destination.txt. ```   |
| `fs.mkdir()`              | Creates a new directory.                                                                       | `path`, `options` (optional)                                | `Promise<void>`                               | ```javascript await fs.mkdir('newDir'); // Creates a directory named newDir. ```                                   |
| `fs.readdir()`            | Reads the contents of a directory.                                                             | `path`, `options` (optional)                                | `Promise<string[]>`                          | ```javascript const files = await fs.readdir('myDir'); // Returns an array of filenames in myDir. ```              |
| `fs.readFile()`           | Reads the entire contents of a file.                                                           | `path`, `options` (optional)                                | `Promise<Buffer|string>`                      | ```javascript const data = await fs.readFile('file.txt', 'utf-8'); // Reads file.txt as a string. ```             |
| `fs.rename()`             | Renames a file or directory.                                                                    | `oldPath`, `newPath`                                       | `Promise<void>`                               | ```javascript await fs.rename('oldName.txt', 'newName.txt'); // Renames oldName.txt to newName.txt. ```            |
| `fs.rmdir()`              | Removes a directory.                                                                             | `path`                                                      | `Promise<void>`                               | ```javascript await fs.rmdir('oldDir'); // Removes the directory named oldDir. ```                                  |
| `fs.stat()`               | Returns information about a file or directory.                                                | `path`                                                      | `Promise<fs.Stats>`                          | ```javascript const stats = await fs.stat('file.txt'); // Returns stats about file.txt. ```                        |
| `fs.unlink()`             | Deletes a file.                                                                                | `path`                                                      | `Promise<void>`                               | ```javascript await fs.unlink('file.txt'); // Deletes file.txt. ```                                                |
| `fs.writeFile()`          | Writes data to a file, replacing the file if it already exists.                              | `path`, `data`, `options` (optional)                       | `Promise<void>`                               | ```javascript await fs.writeFile('file.txt', 'Hello World!'); // Writes "Hello World!" to file.txt. ```          |



| **Promise Feature/Method**      | **Description**                                                                                       | **Example**                                                                                                         |
|----------------------------------|-------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Creating a Promise**           | Use the `Promise` constructor to create a new Promise object.                                        | ```javascript const myPromise = new Promise((resolve, reject) => { // Asynchronous operation }); ```              |
| **Resolving a Promise**          | Call the `resolve` function to fulfill the Promise successfully.                                      | ```javascript const myPromise = new Promise((resolve) => { resolve('Success!'); }); ```                            |
| **Rejecting a Promise**          | Call the `reject` function to mark the Promise as failed.                                            | ```javascript const myPromise = new Promise((_, reject) => { reject('Error!'); }); ```                             |
| **Using .then()**                | Attach callbacks for when the Promise is fulfilled (resolved).                                        | ```javascript myPromise.then((result) => { console.log(result); }); // Output: Success! ```                      |
| **Using .catch()**               | Attach a callback for when the Promise is rejected (failed).                                         | ```javascript myPromise.catch((error) => { console.error(error); }); // Output: Error! ```                       |
| **Using .finally()**             | Attach a callback that runs when the Promise is settled (fulfilled or rejected), regardless of outcome. | ```javascript myPromise.finally(() => { console.log('Promise settled.'); }); ```                                 |
| **Chaining Promises**            | You can chain multiple `.then()` calls to perform sequential asynchronous operations.                 | ```javascript myPromise.then((result) => { return anotherPromise; }).then((finalResult) => { console.log(finalResult); }); ``` |
| **Promise.all()**                | Run multiple Promises in parallel and wait for all of them to resolve or for any to reject.         | ```javascript Promise.all([promise1, promise2]).then((results) => { console.log(results); }); ```              |
| **Promise.race()**               | Returns a Promise that resolves or rejects as soon as one of the Promises in the iterable resolves or rejects. | ```javascript Promise.race([promise1, promise2]).then((result) => { console.log(result); }); ```               |
| **Promise.allSettled()**         | Waits for all Promises to settle (either resolved or rejected) and returns their results.            | ```javascript Promise.allSettled([promise1, promise2]).then((results) => { console.log(results); }); ```       |

### .then/catch vs async
| Feature                | `.then()` / `.catch()`                              | `async` / `await`                                  |
|------------------------|-----------------------------------------------------|-----------------------------------------------------|
| **Syntax**             | Uses method chaining to handle promises.            | Uses `async` keyword before a function and `await` to pause execution. |
| **Example**            | ```javascript                                        | fetch('url')                                       | 
|                        |   .then(response => response.json())               |   .then(data => console.log(data))                |
|                        |   .catch(error => console.error(error));           |   .catch(error => console.error(error));           |
|                        | ```                                                 | ```                                               |
|                        |                                                     | async function fetchData() {                       |
|                        |                                                     |   try {                                          |
|                        |                                                     |     const response = await fetch('url');         |
|                        |                                                     |     const data = await response.json();           |
|                        |                                                     |     console.log(data);                            |
|                        |                                                     |   } catch (error) {                              |
|                        |                                                     |     console.error(error);                         |
|                        |                                                     |   }                                               |
|                        |                                                     | }                                                 |
|                        |                                                     | fetchData();                                      |
|                        | ```                                                 | ```                                               |
| **Error Handling**     | Uses `.catch()` method to handle errors.           | Uses `try/catch` block to manage errors.           |
| **Readability**        | Can lead to callback hell with multiple chained calls. | More readable and resembles synchronous code structure. |
| **Debugging**          | Each `.then()` and `.catch()` can be independently debugged, but can become cumbersome. | Easier to follow the flow of asynchronous code, making debugging simpler. |
| **Use Cases**          | Suitable for simple promise chains.                 | Preferred for more complex asynchronous logic or when handling multiple asynchronous operations. |
| **Return Values**      | Can return promises, allowing chaining.             | Can return values directly, making it easier to manage results. |
| **Control Flow**       | Promises resolve in the order they are created.     | Execution pauses at each `await`, allowing for easier sequencing of operations. |

### promise creation
    // 1. Create a Promise: Use the Promise constructor to create a new Promise object. The constructor takes a function (executor) that receives two parameters: resolve and reject.
    const myPromise = new Promise((resolve, reject) => {
        // Your asynchronous code goes here
    });

    // 2. Execute Asynchronous Code: Inside the executor function, perform the asynchronous operation (e.g., API call, file read).
    const myPromise = new Promise((resolve, reject) => {
        // Simulating an asynchronous operation (e.g., fetching data)
        setTimeout(() => {
            const success = true; // Simulate success or failure
            if (success) {
                resolve("Data fetched successfully!"); // Call resolve on success
            } else {
                reject("Error fetching data."); // Call reject on failure
            }
        }, 1000);
    });

    // 3. Handle the Promise Result: Use .then() to handle the resolved value and .catch() to handle any errors.
    myPromise
        .then(result => {
            console.log(result); // Logs the resolved value
        })
        .catch(error => {
            console.error(error); // Logs the error if rejected
        });

    // 4. Chaining Promises: You can return another promise from within a .then() block to chain further operations.
    myPromise
        .then(result => {
            console.log(result);
            return new Promise((resolve) => {
                setTimeout(() => {
                    resolve("Second operation completed.");
                }, 500);
            });
        })
        .then(secondResult => {
            console.log(secondResult);
        })
        .catch(error => {
            console.error(error);
        });

    // 5. Using async/await Syntax: Alternatively, you can use async/await to work with promises in a more synchronous style.
    async function fetchData() {
        try {
            const result = await myPromise; // Wait for the promise to resolve
            console.log(result);
        } catch (error) {
            console.error(error); // Handle any errors
        }
    }

    fetchData(); // Call the async function



```javascript
//generated examples below
// Promise Examples in JavaScript

// 1. Basic Promise Creation
const basicPromise = new Promise((resolve, reject) => {
    // Simulating an asynchronous operation using setTimeout
    setTimeout(() => {
        // Resolving the Promise after 2 seconds
        resolve('Basic Promise Resolved!');
    }, 2000);
});

// Handling the resolved value
basicPromise.then(result => {
    console.log(result); // Output after 2 seconds: Basic Promise Resolved!
});


// 2. Promise with Rejection
const rejectPromise = new Promise((resolve, reject) => {
    // Simulating an asynchronous operation that fails
    setTimeout(() => {
        // Rejecting the Promise after 1.5 seconds
        reject('Promise Rejected!');
    }, 1500);
});

// Handling the rejection
rejectPromise.catch(error => {
    console.error(error); // Output after 1.5 seconds: Promise Rejected!
});


// 3. Chaining Promises
const firstPromise = new Promise((resolve) => {
    setTimeout(() => {
        resolve('First Promise Resolved');
    }, 1000);
});

// Chaining a second Promise that resolves after the first one
firstPromise
    .then(result => {
        console.log(result); // Output after 1 second: First Promise Resolved
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve('Second Promise Resolved');
            }, 1000);
        });
    })
    .then(result => {
        console.log(result); // Output after 2 seconds: Second Promise Resolved
    });


// 4. Using Promise.all()
const promise1 = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Promise 1 Resolved');
    }, 1000);
});

const promise2 = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Promise 2 Resolved');
    }, 1500);
});

// Running multiple Promises in parallel
Promise.all([promise1, promise2])
    .then(results => {
        console.log(results); 
        // Output after 1.5 seconds: ['Promise 1 Resolved', 'Promise 2 Resolved']
    });


// 5. Using Promise.race()
const promiseA = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Promise A Resolved');
    }, 2000);
});

const promiseB = new Promise((reject) => {
    setTimeout(() => {
        reject('Promise B Rejected');
    }, 1000);
});

// Getting the result of the first Promise that resolves or rejects
Promise.race([promiseA, promiseB])
    .then(result => {
        console.log(result); // Output after 1 second: Promise B Rejected
    })
    .catch(error => {
        console.error(error); // This will catch the rejection from Promise B
    });


// 6. Using Promise.allSettled()
const promiseX = new Promise((resolve) => {
    setTimeout(() => {
        resolve('Promise X Resolved');
    }, 1000);
});

const promiseY = new Promise((reject) => {
    setTimeout(() => {
        reject('Promise Y Rejected');
    }, 500);
});

// Wait for all Promises to settle (resolve or reject)
Promise.allSettled([promiseX, promiseY])
    .then(results => {
        console.log(results); 
        // Output after 1 second: 
        // [
        //   { status: 'fulfilled', value: 'Promise X Resolved' },
        //   { status: 'rejected', reason: 'Promise Y Rejected' }
        // ]
    });


// 7. Error-First Callback Style with Promises
function fetchData() {
    return new Promise((resolve, reject) => {
        const error = false; // Change to true to simulate an error
        if (error) {
            reject('Data fetch failed!');
        } else {
            resolve('Data fetched successfully!');
        }
    });
}

// Handling the success or failure of the fetchData Promise
fetchData()
    .then(data => {
        console.log(data); // Output: Data fetched successfully!
    })
    .catch(err => {
        console.error(err); // Output: Data fetch failed! (if error is true)
    });


// 8. Promise with a Timeout
function timeoutPromise(ms) {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve(`Resolved after ${ms} milliseconds`);
        }, ms);
    });
}

// Using the timeoutPromise function
timeoutPromise(3000).then(result => {
    console.log(result); // Output after 3 seconds: Resolved after 3000 milliseconds
});
```
### arman promise notes
```javascript
//note examples

Questions we want to answer: 
1) How do we create a promise
2) How do we change the status of the promise
3) How do we listen for when the status of a promise changes
*/

// (1) Simple way to create a promise
let promise = new Promise();

// (2) How do you change the state of the promise
let promise = new Promise();
// We give the promise a single callback function, that takes in two 
// functions, resolve and reject

// When you call resolve(), the status changes to fulfilled
// When you call reject(), the status changes to rejected

let promise = new Promise((resolve, reject) => {
	resolve()  // promise is fulfilled
	reject()  //  promise is rejected
});

// Let's take a look at what a promise is exactly

// Open chrome dev tools and write the following below
let promise = new Promise((resolve, reject) => {
});

console.log(promise);

// Notice it's just an object. 
// Now we have a special thing call proto, which basically is a bunch
// of hidden methods we can call on this object. We are interested in 
// then and catch

// When a promise state changes to fulfilled (which happens when we call resolve)
// the function that we pass to "then" will be called. 

// When a promise state changes to rejected (which happens when we call reject)
// the function that we pass to "catch" will be called

// Time for you to test things out==================================

// Create two functions, onResolved and onRejected. Inside each function, 
// console.log "success" and "error" respectively. 


// Create a new promise, which takes a function contained resolve and reject
// as parameters. In the function body, timeout for 3 seconds, then call
// resolve(). Now make another promise, which takes again a resolve and reject,
// but this time call reject. Again, timeout for 3 seconds. Do this in chrome
// devtools. 

// finally, call .then() and .catch() on your promise, passing your
// onResolved and onRejected parameters respectively. 

// Sample Solution
function onResolved() {
	console.log("success");
}

function onRejected() {
	console.log("error");
}

var promise = new Promise((resolve, reject) => {
	setTimeout(() => {
	resolve() //fulfilled
	}, 3000)
});

promise
.then(onResolved)
.catch(onRejected);

// We create a promise. After 3 seconds, it calls resolve. This means
// our .then will trigger, calling our onResolved function. 

// if we call reject() instead of resolve, our onRejected will be called. 


// Let's now do some practice with Node.js and promises

// Try and convert fs.readFile() into a promise. It uses a callback by default
// call your function  

// call your function readFilePromise

// Sample Solution
function readFilePromise(filename) {
    return new Promise(function(resolve, reject) {
        fs.readFile(filename, function(err, data){
            if (err) 
                reject(err); 
            else 
                resolve(data);
        });
    });
};

// small note: we can also write our function like so

let readFilePromise = function(filename) {
    return new Promise(function(resolve, reject) {
        fs.readFile(filename, function(err, data){
            if (err) 
                reject(err); 
            else 
                resolve(data);
        });
    });
};

// one interesting advantage of this syntax is that I can easily refactor
// it to do something really interesting. I can make it part of the fs module.

fs.readFilePromise = function(filename) {
    return new Promise(function(resolve, reject) {
        fs.readFile(filename, function(err, data){
            if (err) 
                reject(err); 
            else 
                resolve(data);
        });
    });
};


// Remember the issues we had with callbacks earlier? 
// - Hard to read
// - no centralized error handling

// You can see how we fixed both these issues 

//===============================================================
// Recall what we had earlier
function multiplier(number1, number2, callback) {
    if (typeof number1 !== 'number' || typeof number2 !== 'number') 
      callback(new Error('the first and second arguments must be number'));
      const result = parseInt(number1) * parseInt(number2);
      callback(null, result);
}

multiplier(3, 4, function(err, result) {
	if(err) {
		console.log(err);
	} else {
		console.log(result);
	}
});

// Try and convert this into a Promise

// Sample Solution
function multiplier(number1, number2) {
  return new Promise((resolve, reject) => {
    if (typeof number1 !== 'number' || typeof number2 !== 'number') 
      reject(new Error('the first and second arguments must be number'));
      const result = parseInt(number1) * parseInt(number2);
      resolve(result);
  });
}

// Actually calling our function and dealing with the promise

// .then, gets the result
multiplier(1, 2).then(data => {
  // now data is 1 * 2 = 2
  // ...
});
// .catch, catchs the error
multiplier(1, 'a').catch(error => {
  // now the error is about the fact that 'a' is not a number
  // ...
});
let getSpacedData = (fileName) => {
	return new Promise((resolve, reject) => {
    if (typeof fileName !== "string") {
			reject("Please enter a string for the file name")
    } else {
      fs.readFile(fileName, "utf8", (err, data) => {
				if (err) {
					reject(err);
        } else {
					resolve(data.split(" "))
        }
      })
    }
  })
}

let filterEvens = (arr) => {
  return arr.filter(item => item % 2 == 0)
}

getSpacedData("spacedNumbers.txt")
  .then(filterEvens)
  .then(data => console.log(data));

```
### if err to promise
```javascript
fs.readFile("file1.txt", "utf8", (err, fileTwo) => {
    if (err) {
        return console.log(err);
    }
    fs.readFile(fileTwo, "utf8", (err, fileThree) => {
        if (err) {
            return console.log(err);
        }
        fs.readFile(fileThree, "utf8", (err, fileFour) => {
            if (err) {
                return console.log(err);
            }
            fs.readFile(fileFour, "utf8", (err, fileFourResult) => {
                if (err) {
                    return console.log(err);
                }
                console.log(`Contents of file4: ${fileFourResult}`);
                
            })
        })
    })
})
// becomes

const fs = require("fs");

let readFilePromise = (fileName) => {
    return new Promise((resolve, reject) => {
        fs.readFile(fileName, "utf8", (err, data) => {
            if (err) {
                reject(err);
            } else {
                resolve(data);
            }
        })
    })
}

readFilePromise("file1.txt")
    .then(fileTwo => readFilePromise(fileTwo))
    .then(fileThree => readFilePromise(fileThree))
    .then(fileFour => readFilePromise(fileFour))
    .then((res) => console.log(res))
    .catch(err => console.log(err))

```
## labs
### teacher code example
```javascript

//distance lab prof answer
const squareRoot = (num) => Math.sqrt(num);

const square = (num) => num * num;

const distance = (x1, y1, x2, y2) => {
  return squareRoot(square(x2 - x1) + square(y2 - y1));
};

module.exports = { distance };
//-------------- Seperate File----------------------
const { argv } = require("process");
const { distance } = require("./mathHelpers");
const fs = require("fs");
const path = require("path");
const folderPath = "dataPoints";
const fileName = "points.txt";
const os = require("os");
const filePath = path.join(__dirname, folderPath, fileName);

// destructure args from the process.argv array
const [, , x1, y1, x2, y2] = argv;

// A function called processInput receive userInput ✅
const processInput = (userInput) => {
  // Create a folder called dataPoints ✅
  fs.mkdir("dataPoints", (err) => {
    if (err) {
      return console.log(err);
    }
    // Create a file called points.txt in ./d    atapoints folder
    // write userInput info into points.txt ✅
    fs.writeFile(filePath, userInput, (err) => {
      if (err) {
        return console.log(err);
        // recursive call to processInput goes here
      }
      // print a content saved ✅
      console.log("Content written to file");
      // APPEND the distance message to the end of our file

      const distanceCalculation = distance(
        Number(x1),
        Number(y1),
        Number(x2),
        Number(y2)
      );
      const distanceMsg = `${os.EOL}The distance between your two points: (${x1},${y1}), (${x2},${y2}) is ${distanceCalculation}`;
      fs.appendFile(filePath, distanceMsg, (err) => {
        if (err) {
          return console.log(err);
        }
      });
    });
  });
};

processInput(`${x1}, ${y1}, ${x2}, ${y2}`);
```

### word position lab 
```javascript
const wordPosition = (words) => {
    // Convert the input array of words into an array of key-value pairs
    const object = Object.entries(words);
    
    // Create a Map from the array of key-value pairs, where each word is associated with its index
    let flipme = new Map(object);
    
    // Initialize a new Map to store the flipped results (words as keys and their positions as values)
    let flipped = new Map();
    
    // Iterate through each entry in the flipme Map
    flipme.forEach((value, key) => {
        // Check if the flipped Map already has the current value (word)
        if (!flipped.has(value)) {
            // If not, create a new entry in flipped Map with the word as key and an empty array as value
            flipped.set(value, []);
        }
       
        // Push the current key (index) into the array of positions for the corresponding word in flipped Map
        flipped.get(value).push(key);
    });
    
    // Convert the flipped Map back into a plain object, where keys are words and values are arrays of positions
    let output = Object.fromEntries(flipped);
    
    // Log the type of the output to the console (should be 'object')
    console.log(typeof output);
    
    // Return the final output object
    return output;
}

// Define an input array of words with some repetitions
const input = [
  "buy",
  "it",
  "use",
  "it",
  "break",
  "it",
  "fix",
  "it",
  "trash",
  "it",
  "change",
  "it",
  "mail",
  "upgrade",
  "it",
];

// Call the wordPosition function with the input array and store the result
const output = wordPosition(input);

/*
Output should look like so:
{
  break: [ 4 ],
  buy: [ 0 ],
  change: [10],
  fix: [ 6 ],
  it:  [1, 3, 5, 7, 9, 11, 14],
  mail: [ 12 ],
  trash: [ 8 ],
  upgrade: [ 13 ],
  use: [ 2 ],
}
*/

```

### lab 2 math helpers

```javascript

// main file

// formula = d (SQRT ((x2-x1)^2 + (y2-y1)^2))
const { argv } = require('process');
const { distance } = require('./mathHelpers.js');
const fs = require('fs');
const currentDate = Date();

function proccessInput(userInput) { 
    const inputArgs = argv.slice(2); // removes first two args
    // console.log('help');

    if (inputArgs.length !== 4) {
        console.error(' our calculations require 4 input buddyguy!');
    } 
        const x1 = inputArgs[0];
        const x2 = inputArgs[1];
        const y1 = inputArgs[2];
        const y2 = inputArgs[3];

        console.log('you have input', inputArgs);
        console.log(x1,x2,y1,y2);

        const solvedDistance = distance(x1,x2,y1,y2);
        console.log('answer', solvedDistance);
        
        // all variables for calculations isolated
    
    // path and folder creation
    const folderPath = './dataPoints';
    const filePath = './dataPoints/points.txt';
    fs.mkdir(folderPath, { recursive: true }, (err) => {
        if (err) {
            console.error('line 25 folder creation kerfuffle:', err); 
            return;
        }
        else {
            console.log('folder found or created');
        }
    // use fs access fs constraints.f OK to add in more funcitonality or whatever so im not always overwriting
    fs.writeFile(filePath, `${currentDate}\nPoints: (${x1},${y1}), (${x2},${y2})\n`, (err) => {
        if (err) {
            console.error('file kerfuffle see line 36:', err);
            return;
        }

        console.log('content saved');

        // create a return message for the user of points.txt
        const distanceMessage = `The distance between (${x1},${y1}) and (${x2},${y2}) is ${solvedDistance}.\n`;

        fs.appendFile(filePath, distanceMessage, (err) => {
            if (err) {
                console.error('Error appending file:', err);
            } else {
                console.log('Distance appended to the file.');
            }
        });
    });
});


}


proccessInput();  

// mathhelpers
function square(x) {
    return x * x;
    // or x ** 2
}

function squareRoot(x) {
    return Math.sqrt(x);
    // could also do x ** (1/2)
}

function distance(x1, y1, x2, y2) {
    return squareRoot(square(x2-x1) + square(y2-y1));
    // the full calc


}

module.exports = { distance };
```
### lab 3 argv web exports

```javascript
// . program that prints a list of files in a given directory
//. filters by extension of path
//. path is passed as first arg in function
//. file extension for filtering as second arg
//. for example if filter is 'txt' only show txt files
//. 1 file per line for print out
const { argv } = require('process');
const path = require('path');
const fs = require('fs');
const { dir } = require('console');
const pathToParse = argv[2];
const filterExpression = '.' + argv[3];

function listFiles(dirPath, filter) {
    if (!dirPath || !filter) {
        console.error('input incorrect');
    }
    console.log(typeof dirPath);
    fs.readdir(dirPath, (err, files) => {
        if (err) {
            console.error('line 14 error with file parsing');  
        }
        files.forEach((value) => {
            if (path.extname(value) === filterExpression) {
                console.log(value);
            }
        });
    });
}

listFiles(pathToParse, filterExpression);


// main.js
const { argv } = require('process');
const listFiles = require('./module'); 



listFiles(argv[2], argv[3], (err, files) => {
    if (err) {
        console.error('Error processings args:', err.message);
        return;
    }

    console.log(files)

    
});


// module.js
const fs = require('fs');
const path = require('path');

function listFiles(dir, filterExpression, callback) {
    if (!dir || !filterExpression) {
        return callback(new Error('Input incorrect',null)); 
        // missing args
    }

    
    if (filterExpression.includes('.')) {
        filterExpression = filterExpression.replace(/\./g, ''); 
        // Remove all dots
    }

  
    const recognizedExtensions = [
        'txt', 'doc', 'docx', 'pdf', 'xls', 'xlsx',
        'ppt', 'pptx', 'odt', 'rtf', 'jpg', 'jpeg', 'png', 'gif', 'bmp', 'tiff', 'tif',
        'svg', 'webp', 'mp3', 'wav', 'aac', 'flac', 'ogg', 'm4a',
        'mp4', 'avi', 'mov', 'mkv', 'wmv', 'flv',
        'zip', 'rar', 'tar', 'gz', '7z',
        'html', 'htm', 'css', 'js', 'json', 'xml',
        'exe', 'bat', 'sh', 'dll', 'apk',
        'py', 'java', 'c', 'cpp', 'php', 'rb',
        'csv', 'sql', 'db', 'log', 'md', 'ini', 'cfg', 'ics'
    ];
    // i think all file extensions? 

   
    if (!recognizedExtensions.includes(filterExpression)) {
        return callback(new Error('Unrecognized file extension', null)); 
        // falsy extensions
    }
    fs.access(dir, (err) =>{
        if (err) {
            return callback(new Error(' issue with the directory check for typos', null));
        }
 

    fs.readdir(dir, (err, files) => {
        
        if (err) {
            return callback(err, null); 
            // any error on readdir comes back to user
        }

        var filteredFiles = files.filter(function(file) {
            return path.extname(file) === '.' + filterExpression;
        });
        if (filteredFiles.length === 0) {
            return callback(new Error('no matching fileronis')); 
            // user clarity or something
        } else {
            for (let file of filteredFiles) {
                callback(null, file);
              }
            }
         });
        
     });
}

module.exports = listFiles;


```

### lab 4 generated answer
```javascript
// do not blindly use this answer this is just to look at potential promise methods in action

const fs = require("node:fs/promises");
const path = require("node:path");

// Function to register a user
const register = (username, password) => {
    const databasePath = path.join(__dirname, "database.txt");
    
    // Promise to read the database file, returns an empty string if the file doesn't exist
    fs.readFile(databasePath).then(data => {
        // Check if the username already exists in the database
        if (data.includes(username)) {
            throw new Error(`User with username "${username}" already exists.`);
        }

        const entry = `${username}:${password}\n`;
        // Promise to append the new user to the database
        return fs.appendFile(databasePath, entry);
    })
    .then(() => {
        console.log(`User "${username}" registered successfully.`);
    })
    .catch(error => {
        console.error(error.message);
    });
};

// Function to create a blog
const createABlog = (blogName) => {
    const blogPath = path.join(__dirname, blogName);
    // Promise to create the blog directory
    fs.mkdir(blogPath)
        .then(() => {
            console.log(`Blog "${blogName}" created successfully.`);
        })
        .catch(error => {
            if (error.code === "EEXIST") {
                console.error(`Blog with the name "${blogName}" already exists. Please choose another name.`);
            } else {
                console.error(`Error creating blog: ${error.message}`);
            }
        });
};

// Function to create a post
const createPost = (postTitle, postContent, blogName) => {
    const blogPath = path.join(__dirname, blogName);
    
    // Check if the blog directory exists
    fs.access(blogPath)
        .then(() => {
            // Replace spaces with underscores in the post title
            const formattedTitle = postTitle.replace(/ /g, "_");

            // Create a unique filename if it already exists
            let filePath = path.join(blogPath, `${formattedTitle}.txt`);
            let count = 1;

            // While loop to ensure a unique file name
            const checkFileExists = () => {
                return fs.stat(filePath).then(() => {
                    filePath = path.join(blogPath, `${formattedTitle}_${count}.txt`);
                    count++;
                    return checkFileExists();
                }).catch(() => {
                    return filePath; // Return unique file path when it doesn't exist
                });
            };

            return checkFileExists().then(uniqueFilePath => {
                // Promise to write the post content to the file
                const content = `---\nlikes:1\nlikedBy: you\n${postContent}\n---\n`;
                return fs.writeFile(uniqueFilePath, content);
            });
        })
        .then(() => {
            console.log(`Post "${postTitle}" created successfully in blog "${blogName}".`);
        })
        .catch(error => {
            if (error.code === "ENOENT") {
                console.error(`Blog "${blogName}" does not exist. Please create it first.`);
            } else {
                console.error(`Error creating post: ${error.message}`);
            }
        });
};

// Function to like a post
const likePost = (blogName, postTitle, username) => {
    const databasePath = path.join(__dirname, "database.txt");
    // Promise to read the database file
    fs.readFile(databasePath)
        .then(data => {
            const users = data.split("\n").filter(Boolean).map(line => line.split(":")[0]);

            // Check if the username exists
            if (!users.includes(username)) {
                throw new Error(`User "${username}" does not exist.`);
            }

            const blogPath = path.join(__dirname, blogName);
            const formattedTitle = postTitle.replace(/ /g, "_");
            const filePath = path.join(blogPath, `${formattedTitle}.txt`);

            // Promise to read the post file
            return fs.readFile(filePath).then(postData => {
                const lines = postData.split("\n");
                const likesLine = lines[1]; // likes:1
                const likedByLine = lines[2]; // likedBy: you

                // Update likes
                const currentLikes = parseInt(likesLine.split(":")[1], 10);
                const updatedLikes = currentLikes + 1;

                // Update likedBy
                const likedByList = likedByLine.split(":")[1].trim();
                const updatedLikedBy = `${likedByList}, ${username}`;

                // Promise to write the updated content back to the file
                const updatedContent = `${likesLine.split(":")[0]}:${updatedLikes}\n${likedByLine.split(":")[0]}: ${updatedLikedBy}\n${lines.slice(3).join("\n")}`;
                return fs.writeFile(filePath, updatedContent);
            });
        })
        .then(() => {
            console.log(`Post "${postTitle}" liked by "${username}".`);
        })
        .catch(error => {
            if (error.code === "ENOENT") {
                console.error(`Post "${postTitle}" does not exist in blog "${blogName}".`);
            } else {
                console.error(error.message);
            }
        });
};

// Example usage (You can uncomment these to test the functions):
// register('john_doe', 'password123');
// createABlog('my_first_blog');
// createPost('My First Post', 'This is the content of my first post.', 'my_first_blog');
// likePost('my_first_blog', 'My_First_Post', 'john_doe');

```

### lab 5 generated possible answer

```javascript
// generated content do not copy just to see asynch promises

// ioHandler.js
const fs = require('fs').promises;
const path = require('path');
const yauzl = require('yauzl-promise');
const PNG = require('pngjs').PNG;

// Function to unzip files
const unzipFiles = async (zipPath) => {
    const directory = './unzipped'; // Output directory
    await fs.mkdir(directory, { recursive: true }); // Create the directory if it doesn't exist

    const zipFile = await yauzl.open(zipPath);
    const filePromises = [];

    // Iterate through each entry in the zip file
    for (const entry of await zipFile.getEntries()) {
        if (!entry.fileName.endsWith('.png')) continue; // Skip non-PNG files

        const filePath = path.join(directory, entry.fileName);
        // Promise to extract each file
        filePromises.push(
            entry.open().then(readStream => {
                return new Promise((resolve, reject) => {
                    const writeStream = fs.createWriteStream(filePath);
                    readStream.pipe(writeStream);
                    writeStream.on('finish', resolve);
                    writeStream.on('error', reject);
                });
            })
        );
    }

    await Promise.all(filePromises); // Wait for all files to be extracted
    console.log("Extraction operation complete.");
};

// Function to read directory and get PNG files
const readDir = async (dirPath) => {
    const files = await fs.readdir(dirPath);
    const pngFiles = files
        .filter(file => file.endsWith('.png'))
        .map(file => path.join(dirPath, file)); // Return full path

    return pngFiles;
};

// Function to apply grayscale filter
const grayScale = async (pathIn, pathOut) => {
    return new Promise((resolve, reject) => {
        fs.createReadStream(pathIn)
            .pipe(new PNG())
            .on('parsed', function () {
                for (let i = 0; i < this.data.length; i += 4) {
                    const avg = (this.data[i] + this.data[i + 1] + this.data[i + 2]) / 3; // Calculate average
                    this.data[i] = avg;     // Red
                    this.data[i + 1] = avg; // Green
                    this.data[i + 2] = avg; // Blue
                }
                // Save the new image
                this.pack().pipe(fs.createWriteStream(pathOut))
                    .on('finish', resolve) // Resolve when finished
                    .on('error', reject);  // Reject on error
            })
            .on('error', reject); // Handle errors
    });
};

module.exports = { unzipFiles, readDir, grayScale };

```

### practice question possible asnwer
```javascript
lunch,bento box b - sashimi,box combo,$9.59
dinner,vegetable sushi,6 rolls,$3.50
dinner,tuna roll,3 rolls,$4.50
dinner,roe,2 rolls,$3.95
lunch,bento box a - chicken teriyaki,box combo,$8.59
dessert,cheesecake,1 slice,$8.00

// asyncCallbackSolution.js
const fs = require('fs');

// Read the CSV file
fs.readFile('menu.csv', 'utf8', (err, data) => {
    if (err) {
        return console.error('Error reading the CSV file:', err);
    }

    const lines = data.split('\n');
    const mealTotals = {
        lunch: { total: 0, items: [] },
        dinner: { total: 0, items: [] },
        dessert: { total: 0, items: [] },
    };

    // Parse the CSV data
    lines.forEach(line => {
        const [mealType, mealName, quantity, price] = line.split(',');
        const priceValue = parseFloat(price.replace('$', ''));

        if (mealType && mealName && quantity && !isNaN(priceValue)) {
            mealTotals[mealType].total += priceValue;
            mealTotals[mealType].items.push(`${price.trim()} ${mealName.trim()}`);
        }
    });

    // Prepare the output content
    let output = '';

    for (const mealType in mealTotals) {
        if (mealTotals[mealType].items.length > 0) {
            output += `* ${mealType.charAt(0).toUpperCase() + mealType.slice(1)} Items *\n`;
            mealTotals[mealType].items.forEach(item => {
                output += item + '\n';
            });
            output += `Total: $${mealTotals[mealType].total.toFixed(2)}\n\n`;
        }
    }

    // Write to the output file
    fs.writeFile('menu.txt', output.trim(), (err) => {
        if (err) {
            return console.error('Error writing the TXT file:', err);
        }
        console.log('Menu converted to menu.txt successfully using callbacks!');
    });
});


// promisesSolution.js
const fs = require('fs/promises');

const convertCSVToTXT = async () => {
    try {
        // Read the CSV file
        const data = await fs.readFile('menu.csv', 'utf8');
        
        const lines = data.split('\n');
        const mealTotals = {
            lunch: { total: 0, items: [] },
            dinner: { total: 0, items: [] },
            dessert: { total: 0, items: [] },
        };

        // Parse the CSV data
        for (const line of lines) {
            const [mealType, mealName, quantity, price] = line.split(',');
            const priceValue = parseFloat(price.replace('$', ''));

            if (mealType && mealName && quantity && !isNaN(priceValue)) {
                mealTotals[mealType].total += priceValue;
                mealTotals[mealType].items.push(`${price.trim()} ${mealName.trim()}`);
            }
        }

        // Prepare the output content
        let output = '';

        for (const mealType in mealTotals) {
            if (mealTotals[mealType].items.length > 0) {
                output += `* ${mealType.charAt(0).toUpperCase() + mealType.slice(1)} Items *\n`;
                mealTotals[mealType].items.forEach(item => {
                    output += item + '\n';
                });
                output += `Total: $${mealTotals[mealType].total.toFixed(2)}\n\n`;
            }
        }

        // Write to the output file
        await fs.writeFile('menu.txt', output.trim());
        console.log('Menu converted to menu.txt successfully using Promises!');
    } catch (err) {
        console.error('Error:', err);
    }
};

// Call the function to execute the conversion
convertCSVToTXT();

```


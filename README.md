# js-code-linter

js-code-linter is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code.It is inspired from ESlint, JSLint and JSHint with a few exceptions:

* js-code-linter uses [Espree](https://github.com/eslint/espree) for JavaScript parsing.
* js-code-linter uses an AST to evaluate patterns in code.
* js-code-linter is completely pluggable, every single rule is a plugin and you can add more at runtime.

## Installation and Usage

Prerequisites: Node.js (^12.22.0, ^14.17.0, or >=16.0.0) built with SSL support. (If you are using an official Node.js distribution, SSL is always built in.)

To install run this command:
```
npm i js-code-linter
```
After that, you can run js-code-linter on any file or directory like this:
```
node_modules/js-code-linter/src/index.js --file <file-path.js>
```
## Configuration
To configure in your project add below line in `package.json`.
```
"lint": "node_modules/js-code-linter/src/index.js",
```
After that, you can run js-code-linter in project using `npm run lint` commad.

example:
```
npm run lint --  --file <file-path.js>
```
## What js-code-linter lints ?
js-code-linter performs linting on your JavaScript code, primarily focusing on identifier (variable) declarations and the use of quotes.

It generates a new file `<file-name>.linted.js` with all the tranformation.

Also give error message with line of code where the lint issue is present.
### Identifier Transformations
Variable Declaration Type Optimization:

1. js-code-linter automatically optimizes:
    - variable declarations by transforming `var` identifiers to `let` or `const` as needed.

2. Reassignment Analysis:
     - It identifies variables whose values are reassigned and   transforms them from `var` or `const` to `let`.

3. Constant Declaration:
    - Variables that are never reassigned are transformed from `var` or `let` to `const` for better code consistency.

### Quote Transformation
- Double to Single Quote Conversion:
`js-code-linter` convert double quotes `""` to single quotes `''` for consistent quoting style.

## Output File
- After linting your code, js-code-linter generates a new file named `<file-name>.linted.js`, which includes all the transformations. This file is created in the same directory as the original file.

## Error Messages
- js-code-linter provides error messages that pinpoint the location of linting issues in your code. Each error message includes the clickable line & column number, making it easy to identify and fix problems in your code.

![lint issues](https://i.ibb.co/M68R42S/lint-issues.png)
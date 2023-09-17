# Codelint

Codelint is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code. In many ways, it is similar to JSLint and JSHint with a few exceptions:

* Codelint uses [Espree](https://github.com/eslint/espree) for JavaScript parsing.
* Codelint uses an AST to evaluate patterns in code.
* Codelint is completely pluggable, every single rule is a plugin and you can add more at runtime.

## Installation and Usage

Prerequisites: Node.js (^12.22.0, ^14.17.0, or >=16.0.0) built with SSL support. (If you are using an official Node.js distribution, SSL is always built in.)


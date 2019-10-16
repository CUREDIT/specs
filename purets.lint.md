## Lint config for pure ts in angular and vue 


Immutability rules

* readonly-keyword
* readonly-array
* no-let
* no-array-mutation, ignore-new-array
* no-object-mutation
* no-method-signature
* no-delete

Functional style rules

* no-mixed-interface
* no-expression-statement
* no-if-statement*
* no-loop-statement
* no-throw
* no-try
* no-reject

Allow local mutations sparingly 

* ignore-local
* ignore-prefix 
* ignore-suffix
* no-var-keyword
* no-parameter-reassignment
* "typedef": [true, "call-signature"]

*no-if and no-switch would require a small util.ts file to be added for the functional replacements for if and switch 

read:
https://github.com/jonaskello/tslint-immutable/blob/master/README.md
no-class and no-this is not possible for angular 

prefer unary functions 
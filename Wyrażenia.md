**Wyrażenie** (expression) - fragmenty kodu, które mogą być przetworzone i zamienione na wartość końcową.

### Arithmetic expressions
Under this category go all expressions that evaluate to a number:
```
1 / 2
i++
i -= 2
i * 2
```
### String expressions
Expressions that evaluate to a string:
```
'A ' + 'string'
'A ' += 'string'
```
### Primary expressions
Under this category go variable references, literals and constants:
```
2
0.02
'something'
true
false
this //the current object
undefined
i //where i is a variable or a constant
```
but also some language keywords:
```
function
class
function* //the generator function
yield //the generator pauser/resumer
yield* //delegate to another generator or iterator
async function* //async function expression
await //async function pause/resume/wait for completion
/pattern/i //regex
() // grouping
```
### Array and object initializers expressions
```
[] //array literal
{} //object literal
[1,2,3]
{a: 1, b: 2}
{a: {b: 1}}
```
### Logical expressions
Logical expressions make use of logical operators and resolve to a boolean value:
```
a && b
a || b
!a
```
### Left-hand-side expressions
```
new //create an instance of a constructor
super //calls the parent constructor
...obj //expression using the spread operator
```
### Property access expressions
```
object.property //reference a property (or method) of an object
object[property]
object['property']
```
### Object creation expressions
```
new object()
new a(1)
new MyRectangle('name', 2, {a: 4})
```
### Function definition expressions
```
function() {}
function(a, b) { return a * b }
(a, b) => a * b
a => a * 2
() => { return 2 }
```
### Invocation expressions
The syntax for calling a function or method
```
a.x(2)
window.resize()
```
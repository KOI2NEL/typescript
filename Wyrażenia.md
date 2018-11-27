**Wyrażenie** (expression) - fragmenty kodu, które mogą być przetworzone i zamienione na wartość końcową.

### Arytmetyczne
Wyrażenia rozpoznawane jako liczby
```
1 / 2
i++
i -= 2
i * 2
```
### Łańcuchy znaków
Wyrażenia rozpoznawane jako łańcuchy tekstowe
```
'A ' + 'string'
'A ' += 'string'
```
### Podstawowe / pierwotne
Referencje, literały i stałe
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
oraz słowa kluczowe
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
### Tablice i obiekty
```
[] //array literal
{} //object literal
[1,2,3]
{a: 1, b: 2}
{a: {b: 1}}
```
### Logiczne
Zwracają wartość logiczną
```
a && b
a || b
!a
```
### Lewostronne
```
new //create an instance of a constructor
super //calls the parent constructor
...obj //expression using the spread operator
```
### Dostęp do własności obiektu
```
object.property //reference a property (or method) of an object
object[property]
object['property']
```
### Inicjujące obiekt
```
new object()
new a(1)
new MyRectangle('name', 2, {a: 4})
```
### Definiujące funkcje
```
function() {}
function(a, b) { return a * b }
(a, b) => a * b
a => a * 2
() => { return 2 }
```
### Uruchamiające
Składnia wywołania funkcji i metod
```
a.x(2)
window.resize()
```
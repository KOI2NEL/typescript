W Java Script zmienne są **kontenerami** do przechowywania wartości danych.
* zmienne muszą być unikalnymi identyfikatorami
* zmienną trzeba zadeklarować przed jej użyciem za pomocą `var`, `let` lub `const`
* zmiennej można przypisać wartość
* zmiennej można przypisać wartość w momencie deklaracji
* zmienne można deklarować w linii lub w wielu liniach

**Scope** - to zakres kodu w którym zmienna jest widoczna

### Var
* Zmienna `var` zadeklarowana poza funkcją, jest przypisana do globalnego obiektu okna, jest zmienną globalną
* Zmienna `var` zadeklarowana wewnątrz funkcji jest widoczna w całym ciele danej funkcji

**Hoisting** - przed wykonaniem kodu Java Script "przenosi" deklaracje zmiennych i funkcji "na górę" bieżącego zakresu kodu
```
var a //typeof a === 'undefined'
var x = 5;
var y = 6;
var z = x + y;
```
```
var carName = "Volvo";
```
```
var carName;
carName = "Volvo";
```
```
var person = "John Doe", carName = "Volvo", price = 200;
```
```
var person = "John Doe",
carName = "Volvo",
price = 200;
```

### Let

### Const
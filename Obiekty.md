## Dziedziczenie prototypu
* Każdy obiekt w Java Script posiada właściwość `prototype`, która wskazuje na inny obiekt
* Ten inny obiekt to prototyp obiektu
* Obiekt używa prototypu by po nim dziedziczyć właściwości i metody
* Odziedziczone z prototypu metody i właściwości można w obiekcie nadpisać

Utworzenie obiektu:
```
const car = {}
// lub
const car = new Object()
```
W tym przypadku prototypem obiektu `car` jest `Object`

W przypadku tablicy:
```
const list = []
// lub
const list = new Array()
```
Prototypem jest `Array`

Weryfikacja prototypu za pomocą gettera `__proto__`:
```
car.__proto__ == Object.prototype //true
car.__proto__ == new Object().__proto__ //true
list.__proto__ == Object.prototype //false
list.__proto__ == Array.prototype //true
list.__proto__ == new Array().__proto__ //true
``` 

`Object.prototype` jest bazowym prototypem dla wszystkich obiektów
 ```
Array.prototype.__proto__ == Object.prototype
```


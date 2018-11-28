* Wszystko w Java Script dzieje się w funkcjach
* Funkcja to blok kodu, samowystarczalny, który można zdefiniować raz i uruchomić w dowolnym momencie
* Funkcja może opcjonalnie przyjąć parametry i zwrócić pojedynczy wynik
* Funkcje w JavaScript to szczególny rodzaj obiektów: obiekty funkcyjne. Ich super-moc polega na tym, że można je wywołać
* Funkcje są uważane za "funkcje pierwszej klasy", ponieważ mogą być **przypisane do wartości** i mogą być **przekazywane jako argumenty** i używane jako **wartość zwracana**.

### Składnia
**Funkcja regularna**
```
function dosomething(foo) {
  // do something
}
```

**Funkcja przypisana do zmiennej**
```
const dosomething = function(foo) {
  // do something
}
```

**Funkcja nazwana przypisana do zmiennej**
```
const dosomething = function dosomething(foo) {
  // do something
}
```

**Funkcja strzałkowa**
```
const dosomething = foo => {
  //do something
}
```

### Parametry

Funkcje mogą posiadać jeden lub więcej parametrów
```
const dosomething = () => {
  //do something
}
const dosomethingElse = foo => {
  //do something
}
const dosomethingElseAgain = (foo, bar) => {
  //do something
}
```

Od ES6 parametry mogą posiadać wartości domyślne
```
const dosomething = (foo = 1, bar = 'hey') => {
  //do something
}
```

### Zwracanie wartości
* Każda funkcja zwraca wartość, domyślnie jest to `undefined`
* Wykonanie funkcji jest kończone wraz zz jej ostatnią linią lub po napotkaniu słowa kluczowego `return`
* Funkcja zwraca tylko jedną wartość
```
const dosomething = () => {
  return 'test'
}
const result = dosomething() // result === 'test'
```
### Zagnieżdżanie funkcji
Funkcja może być zdefiniowana wewnątrz innej funkcji
```
const dosomething = () => {
   const dosomethingelse = () => {}
   dosomethingelse()
   return 'test'
}
```
Funkcja zagnieżdżona ma zasięg przypisany do funkcji w której jest zdefiniowana i nie można jej wywołać z zewnątrz.

### Metody obiektów
Gdy funkcje są używane jako właściwości obiektu, nazywane są wtedy metodami
```
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: function() {
    console.log(`Started`)
  }
}
car.start()
```

### `this` w funkcji strzałkowej
```
const car = {
  brand: 'Ford',
  model: 'Fiesta',
  start: function() {
    console.log(`Started ${this.brand} ${this.model}`)
  },
  stop: () => {
    console.log(`Stopped ${this.brand} ${this.model}`)
  }
}
```
W powyższym przykładzie metoda `stop()` zadziała nieprawidłowo, ponieważ w funkcji strzałkowej wskaźnik `this` wskazuje kontekst funkcji otaczającej, którym w tym przypadku jest obiekt `window`. Wynika z tego, że funkcje strzałkowe nie nadają się do tworzenia metod i konstruktorów obiektów.
```
const link = document.querySelector('#link')
link.addEventListener('click', () => {
  // this === window
})
```
```
const link = document.querySelector('#link')
link.addEventListener('click', function() {
  // this === link
})
```

### IIFE, Immediately Invocated Function Expressions
Konstrukcja IIFE niezwłoczne wywołanie funkcji, zaraz po jej deklaracji
```
;(function dosomething() {
  console.log('executed')
})()
```

W ten sposób można przypisać wynik wykonania funkcji do zmiennej:
```
const something = (function dosomething() {
  return 'something'
})()
```

### Hoisting funkcji
W trakcie przetwarzania skryptu Java Script "przesuwa" deklarację funkcji na "górę" zakresu w której ona się znajduje. Dzięki temu możliwe jest wywołanie funkcji przez jej deklaracją.
```
dosomething()
function dosomething() {
  console.log('did something')
}
```

Jednak w przypadku użycia przypisania nazwanej funkcji do zmiennej, "do góry" przenoszona jest tylko deklaracja zmiennej, ale już nie jej wartość, skutkiem czego taki kod nie zadziała:
```
dosomething()
const dosomething = function dosomething() {
  console.log('did something')
}
```
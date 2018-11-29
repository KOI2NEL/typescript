Wraz z edycją ES6, do Java Script zostały dodane klasy. Jest to tak naprawdę "syntactic sugar" - czyli alternatywny sposób wykorzystania istniejącego już mechanizmu dziedziczenia prototypu obiektu - bardziej czytelny dla programistów innych języków zapis semantyczny.

Przykład definicji klasy:
```
class Person {
  constructor(name) {
    this.name = name
  }
  hello() {
    return 'Hello, I am ' + this.name + '.'
  }
}
```

Przykład użycia klasy:
```
const flavio = new Person('Flavio')
flavio.hello()
```

### Dziedziczenie
Klasa może rozszerzać inną klasę, a obiekt zainicjowany za pomocą klasy będzie posiadać odziedziczone po prototypie metody.
```
class Programmer extends Person {
  hello() {
   return super.hello() + ' I am a programmer.'
  }
}
const flavio = new Programmer('Flavio')
flavio.hello()  // "Hello, I am Flavio. I am a programmer."
```
Z wnętrza klasy można odnieść się do klasy nadrzędnej za pomocą `super`.

**Metody statyczne**
Zwykle metody są definiowane w instancji, a nie w samej klasie. Wyjątkiem są metody statyczne, które nie wymagają powołania instancji klasy bo mogły być wywołane.
```
class Person {
  static genericHello() {
    return 'Hello'
  }
}
Person.genericHello() //Hello
```

**Metody prywatne**
Java Script nie ma wbudowanych mechanizmów tworzenia i obsługi metod prywatnych lub chronionych.

**Gettery i settery**
w klasie można stworzyć metody poprzedzone prefixem `get` lub `set`, pozwalające na dostęp do zmiennej w klasie lub na modyfikację jej wartości.
```
class Person {
  constructor(name) {
    this.name = name
  }
  set name(value) {
    this.name = value
  }
  get name() {
    return this.name
  }
}
```
Jeśli zdefiniujemy tylko getter, zawartość właściwości `name` będzie można tylko odczytać.
```
class Person {
  constructor(name) {
    this.name = name
  }
  get name() {
   return this.name
  }
}
```
Jeśli zdefiniujemy tylko setter, z zewnątrz będzie można tylko zmienić wartość właściwości, ale nie będzie możliwy dostęp do jej wartości z zewnątrz klasy.
```
class Person {
  constructor(name) {
    this.name = name
  }
  set name(value) {
    this.name = value
  }
}
```

W JavaScript obiekty są kolekcjami właściwości i metod, czyli mogą posiadać wiele wartości.  

Metoda (method) jest funkcją, należącą do obiektu.  

Właściwość (property) jest wartością lub zbiorem wartości  (w postaci tablicy lub obiektu), należącego do obiektu.  

JavaScript obsługuje cztery rodzaje obiektów:
* Natywne obiekty, takie jak Array i String.
* Tworzone obiekty.
* Obiekty hostów, takie jak window i document.
* Obiekty ActiveX.

### Obiekty natywne
Język JavaScript dostarcza nam do kilka natywnych/wbudowanych klas, z których możemy korzystać podczas tworzenia skryptów:

* **Number** - reprezentuje liczbę
* **Boolean** - pozwala na konwersję wartości “nie-boolowskich” na boolowskie
* **String** - umożliwia przechowywanie tekstu i manipulowanie nim
* **Array** - służy do przechowywania tablic, czyli zmiennych zawierających wiele wartości
* **Date** - używane jest do pracy z datami
* **Math** - dostarcza funkcji matematycznych realizujących różnego rodzaju obliczenia
* **RegExp** - umożliwia tworzenie wyrażeń regularnych
* **JSON** - prosty format danych

W Java Script prawie "wszystko" jest obiektem:
* Boolean może być obiektem (jeśli zdefiniowany z użyciem „new”)
* Number może być obiektem (jeśli zdefiniowany z użyciem „new”)
* String może być obiektem (jeśli zdefiniowany z użyciem „new”)
* Date jest zawsze obiektem
* Math jest zawsze obiektem
* Regular expression jest zawsze obiektem
* Array jest zawsze obiektem
* Function jest zawsze obiektem
* Object jest zawsze obiektem

Wszystkie wartości, z wyjątkiem wartości prymitywnych, są obiektami.

### Wartości prymitywne
Wartość prymitywna to taka, która nie ma swoich właściwości ani metod. W Java Script wyróżniamy 5 typów prymitywnych:
* string
* number
* boolean
* null
* undefined

Wartości prymitywne są "niemutowalne", czyli nie można ich zmienić.

**W Java Script możemy definiować i tworzyć własne obiekty.**

Obiekt można stworzyć na 3 sposoby:
* Przy użyciu literału obiektu
```  
 var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}; 
```
* Przy użyciu słowa kluczowego `new` 
```
var person = new Object();
person.firstName = "John"; 
person.lastName = "Doe";
person.age = 50; 
person.eyeColor = "blue"; 
```
* Definiując konstruktor obiektu, a następnie tworząc obiekt typu konstruktora

### Właściwości obiektu (properties)
Właściwości obiektu są dostępne na kilka sposobów:
```
objectName.property          // person.age
objectName["property"]       // person["age"]
objectName[expression]       // x = "age"; person[x]
```

Dostęp do właściwości poprzez pętlę for…in:
```
for (key in object) {
    console.log(object[key])
}
```

Dodawanie nowych właściwości:
```
person.nationality = "English";
```

Kasowanie właściwości:
```
delete person.age;   // or delete person["age"]; 
```

**Uwagi:**
* Do tworzenia nazw właściwości (i metod) nie można używać zarezerwowanych słów kluczowych
* Kasowanie za pomocą słowa kluczowego `delete` kasuje zarówno wartość właściwości jak i samą właściwość
* Słowo kluczowe `delete` działa tylko na właściwościach obiektów, nie działa na zmiennych i funkcjach.
* Słowo kluczowe `delete` nie powinno być używane na właściwościach natywnych obiektów w Java Script, w przeciwnym razie grozi to "uszkodzeniem" aplikacji.

**Inny sposób na tworzenie właściwości obiektu:**
```
var person = Object.create(null);
Object.defineProperty(person, 'firstName', {
  value: „Maciej",
  writable: true,
  enumerable: true,
  configurable: true
});
```

Właściwość domyślnie posiada swoją nazwę i wartość. Tak naprawdę posiada jeszcze kilka właściwości:
* Enumerable - jeśli właściwość ma być widoczna podczas iterowania po właściwościach obiektu
* Configurable - jeśli właściwość może być zmieniana i kasowana z obiektu
* Writable - jeśli wartość właściwości może być zmieniana za pomocą operatora przypisania (=) 

### Metody obiektu (methods)

Metody obiektu można wywołać za pomocą:
```
objectName.methodName()
```

Dodawanie nowych metod:
```
person.name = function () {
  return this.firstName + " " + this.lastName;
};
```

Kasowanie metod:
```
delete person.name;   // or delete person["age"]; 
```

**Uwagi:**
* W definicji funkcji słowo kluczowe `this` odnosi się do „właściciela” (kontekstu) funkcji
* Użyte bezpośrednio słowo `this` odnosi się do globalnego obiektu, w przeglądarce www będzie to obiekt window.
* Użyte w funkcji, słowo `this` odnosi się do globalnego obiektu
* W trybie `strict` słowo `this` zwróci wartość undefined, bo tryb ten nie pozwala na domyślne przypisanie kontekstu
```
 "use strict"; 
function myFunction() { 
  return this; 
} 
```

### Prototypy i dziedziczenie

**Tworzenie pustego obiektu**
```
var person = Object.create(null);

Object.defineProperty(person, 'firstName', {
  value: "Maciej",
  writable: true,
  enumerable: true,
  configurable: true
});

Object.defineProperty(person, 'lastName', {
  value: "Walczak",
  writable: true,
  enumerable: true,
  configurable: true
});
```

**Object.create(null)** - tworzy instancję „czystego” obiektu, czyli bez żadnego prototypu. Taki obiekt może być głównym prototypem dla innych obiektów.

**Object.defineProperty(object, name, config)** - metoda ta tworzy właściwości w przekazanym do niej obiekcie. Pozwala na ustawienie konfiguracji właściwości za pomocą obiektu konfiguracyjnego i jego właściwości:
* Value
* Writable
* Enumerable
* Configurable

**Prototyp** - to inaczej wskaźnik w obiekcie do innego obiektu. Kiedy w bieżącym obiekcie próbujemy odwołać się do nieistniejącej w nim właściwości lub metody, JavaScript będzie szukać ich w prototypie danego obiektu - aż do głównego elementy, który nie ma swojego prototypu. W takiej sytuacji JS zwróci wartość undefined.

```
var person = Object.create(null);

Object.defineProperty(person, 'fullName', {
 value: function() {
  return this.firstName + ' ' + this.lastName;
 },
 writable: true,
 enumerable: true,
 configurable: true
});

var man = Object.create(person);

Object.defineProperty(man, 'sex', {
 value: 'mężczyzna',
 writable: true,
 enumerable: true,
 configurable: true
});

var maciek = Object.create(man);

Object.defineProperty(maciek, 'firstName', {
 value: 'Maciej',
 writable: true,
 enumerable: true,
 configurable: true
});

Object.defineProperty(maciek, 'lastName', {
 value: 'Walczak',
 writable: true,
 enumerable: true,
 configurable: true
});

maciek.sex        // "mężczyzna"
maciek.fullName() // "Maciej Walczak"
```

W tym kodzie najpierw tworzymy obiekt `person`, który nie ma swojego prototypu, jest więc najwyżej położonym w strukturze obiektem.

Następnie w obiekcie person tworzymy metodę zwracającą wynik wykonania funkcji. Metoda ta będzie wspólna dla wszystkich instancji obiektów, dla których obiekt person będzie prototypem.

W dalszej kolejności tworzymy obiekt `maciek`, dla którego w metodzie `Object.create(person)` jako prototyp użyliśmy obiektu `person`.

Po utworzeniu właściwości w obiekcie `maciek` i użyciu metody `maciek.fullName()` z jego prototypu, dostajemy wynik wykonania tej metody.

**Tworzenie obiektów za pomocą literałów**

**Literał obiektu** - to składniowo uproszczony sposób tworzenia obiektów.

Literał:
```
var person = { firstName: "Paul", lastName: "Irish" }
```
Klasyczny obiekt:
```
var person = Object.create(Object.prototype);
person.firstName = "Paul";
person.lastName  = "Irish";
```

Najważniejszą cechą tworzenia obiektów za pomocą literałów jest fakt, że każdy tak stworzony obiekt jako prototyp będzie posiadał `Object.prototype`.

**Tworzenie obiektów z zachowaniem dziedziczenia**
```
var fromPrototype = function(prototype, object) {
  var newObject = Object.create(prototype);

  for (var prop in object) {
    if (object.hasOwnProperty(prop)) {
      newObject[prop] = object[prop];      
    }
  }
  return newObject;
};

var person = {
  toString: function() {
    return this.firstName + ' ' + this.lastName;
  }
};

var man = fromPrototype(person, {
  sex: "male"
});

var jeremy = fromPrototype(man, {
  firstName: "Jeremy",
  lastName:  "Ashkenas"
});

jeremy.sex        // "male"
jeremy.toString() // "Jeremy Ashkenas"
```

W tym przykładzie tworzymy najpierw (za pomocą literału) obiekt `person` (ma on w swoim prototypie `Object.prototype`).

Następnie w obiekcie `person` tworzymy metodę `toString()`, która nadpisuje metodę z `Object.prototype`.

Następnie z wykorzystaniem funkcji `fromPrototype`, tworzymy obiekt `man`, którego prototypem jest obiekt `person`.

Na końcu w analogiczny sposób tworzymy obiekt `jeremy`, którego prototypem jest obiekt `man`.

W ten sposób obiekt `jeremy` dziedziczy część właściwości i metod z obiektów będących jego prototypami.
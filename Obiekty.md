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
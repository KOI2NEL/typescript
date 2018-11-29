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

**Składnia** - to zestaw reguł opisujących konstrukcję języka programowania.

Program komputerowy składa się z **listy instrukcji** wykonywanych przez komputer.

W języku Java Script instrukcje takie noszą nazwę **statements** - w języku polskim tłumaczone na **instrukcja** lub **rozkaz**.

### Instrukcje w Java Script składają się z:
* **Values** - wartości: literały (Number, String) i zmiennych
* **Operators** - operatorów (arytmetycznych, logicznych, przypisania)
* **Expressions** - wyrażeń (kombinacja wartości, zmiennych i operatorów)
* **Keywords** - słów kluczowych (określających akcję do wykonania)
* **Comments** - komentarzy
***
###  **Identyfikatory** - to nazwy zmiennych, funkcji, słów kluczowych
* pierwszy znak musi być literą, podkreśleniem(_) lub znakiem $
* pozostałe znaki mogą zawierać litery, cyfry, _, $

Cyfry nie mogą być użyte jako pierwszy znak w nazwie, bo Java Script po pierwszym znaku rozróżnia identyfikatory od liczb.
Java Script jest „Case Sensitive” - czyli wielkość liter ma w nim znaczenie.
```
var lastName = "Doe";
var lastname = "Peterson";
```
***
### Słowa kluczowe
Słowo | Opis znaczenia
--- | ---
*break* | przerywa działanie instrukcji **switch** lub **pętli**
*continue* | pozwala "wyskoczyć" z bieżącego przebiegu pętli i rozpoczyna kolejny
*debugger* | zatrzymuje wykonanie skryptu i wywołuje "debuggera" w przeglądarce
*do...while* | wykonuje w pętli blok instrukcji dopóki zadeklarowany warunek jest spełniony
*for* | wykonuje w pętli blok instrukcji dopóki zadeklarowany warunek jest spełniony
*function* | deklaruje funkcję
*if...else* | wykonuje bloki instrukcji w zależności od zadeklarowanych warunków
*return* | kończy wykonanie funkcji
*switch* | wykonuje bloki instrukcji w zależności od zadeklarowanych przypadków
*try...catch* | implementuje przechwytywanie błędów w bloku instrukcji
*var* | deklaruje zmienną
*let* | deklaruje zmienną
*const* | deklaruje stałą
***
### Komentarze
* jednoliniowe
```
// Change heading:
document.getElementById("myH").innerHTML = "My First Page";
// Change paragraph:
document.getElementById("myP").innerHTML = "My first paragraph.";
```
```
var x = 5;      // Declare x, give it the value of 5
var y = x + 2;  // Declare y, give it the value of x + 2
```
* wieloliniowe
```
/*
The code below will change
the heading with id = "myH"
and the paragraph with id = "myP"
in my web page:
*/
document.getElementById("myH").innerHTML = "My First Page";
document.getElementById("myP").innerHTML = "My first paragraph.";
```
***
### Zmienne
W Java Script zmienne są **kontenerami** do przechowywania wartości danych.
* zmienne muszą być unikalnymi identyfikatorami
* zmienną można zadeklarować
* zmiennej można przypisać wartość
* zmiennej można przypisać wartość w momencie deklaracji
* zmienne można deklarować w linii lub w wielu liniach
```
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
***
### Operatory arytmetyczne
Operator | Opis znaczenia
--- | ---
*+* | dodawanie
*-* | odejmowanie
*\** | mnożenie
*/* | dzielenie
*%* | modulo (reszta z dzielenia)
*++* | inkrementacja (zwiekszenie o 1)
*--* | dekrementacja (zmniejszenie o 1)
***
### Operatory przypisania
Operator | Przykład | Odpowiednik
--- | --- | ---
*=* | x = y | 
*+=* | x += y | x = x + y
*-=* | x -= y | x = x - y
*\*=* | x *= y | x = x * y
*/=* | x /= y | x = x / y
*%=* | x %= y | x = x % y
***
### Operatory porównania
Operator | Opis znaczenia
--- | ---
*==* | równa wartość
*===* | równa wartość i typ
*!=* | różna wartość
*!==* | różna wartość i typ
*>* | większe
*<* | mniejsze
*>=* | większe równe
*<=* | mniejsze równe
*?* | operator trójskładnikowy
***
### Operatory logiczne
Operator | Opis znaczenia
--- | ---
*&&* | logiczne "i"
*\|\|* | logiczne "lub"
*!* | logiczne "nie" (negacja)
***
### Operatory typu
Operator | Opis znaczenia
--- | ---
*typeof* | zwraca typ zmiennej
*instanceof* | zwraca "true" jeśli obiekt jest instancją typu obiekt
***
### Typy danych
Java Script jest językiem o dynamicznym typowaniu danych. Oznacza to, że te same zmienne mogą być użyte do przechowywania różnych typów danych.
Typy danych można podzielić na 2 grupy:
* **typy prymitywne**

Typ | Opis 
--- | ---
*string* | łańcuch tekstowy
*number* | liczba
*boolean* | wartość logiczna (true/false)
*undefined* | brak wartości

* **typy złożone**

Typ | Opis 
--- | ---
*function* | funkcja
*object* | obiekt, tablica, null
***
### Funkcje
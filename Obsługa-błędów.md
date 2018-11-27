## Wyjątki (Exceptions)

### Utworzenie wyjątku
Wyjątek jest tworzony za pomocą słowa kluczowego `throw`
```
throw value
```
gdzie `value` może być dowolną wartością, taką jak `string`, `number`, czy `object`.

Gdy Java Script napotka takie żądanie, normalny bieg skryptu jest zatrzymywany i program przechodzi do najbliższej obsługi wyjątku.

### Obsługa wyjątków
```
try {
  //lines of code
} catch (e) {

}
```
`e` jest w tym przypadku wartością wyjątku.

Można dodać wiele obsług wyjątków, by reagować na różne rodzaje błędów.

### finally
Blok `finally` może zawierać kod wykonywany zawsze, niezależnie czy nastąpi poprawne wykonanie kodu czy obsługa wyjątku.
```
try {
  //lines of code
} catch (e) {

} finally {

}
```
```
try {
  //lines of code
} finally {

}
```

### Zagnieżdżanie bloków `try`
```
try {
  //lines of code
  try {
    //other lines of code
  } finally {
    //other lines of code
  }
} catch (e) {

}
```
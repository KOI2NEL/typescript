**Inicjowanie tablicy**
```
const a = []
const a = [1, 2, 3]
const a = Array.of(1, 2, 3)
const a = Array(6).fill(1) //init an array of 6 items of value 1
```
Zalecane jest NIE STOSOWANIE starej składni:
```
const a = new Array() //never use
const a = new Array(1, 2, 3) //never use
```

### Podstawowe operacje na tablicach

**Pobranie długości tablicy**
```
const l = a.length
```

**Iterowanie po tablicy**
```
a.every(f)  // Iterates a until f() returns false
a.some(f)   // Iterates a until f() returns true
const b = a.map(f)  // Iterates a and builds a new array with the result of executing f() on each a element

/* Iterates a and builds a new array with elements of a that returned true when executing
* f() on each a element
*/
const b = a.filter(f)

/* reduce() executes a callback function on all the items of the array and allows to progressively
* compute a result. If initialValue is specified, accumulator in the first iteration will equal to
* that value. 
*/
a.reduce((accumulator, currentValue, currentIndex, array) => {
  // ...
}, initialValue))

a.forEach(f) // Iterates f on a without a way to stop

for (let v of a) {
 console.log(v)
}

for (let i = 0; i < a.length; i += 1) {
  //a[i]
}
```

**Dodanie elementu do tablicy**
```
a.push(4) // na końcu tablicy
a.unshift(0) // na początku
```

**Usunięcie elementu z tablicy**
```
a.pop() // usunięcie z końca
a.shift() // z początku

// z dowolnej pozycji
a.splice(0, 2) // get the first 2 items
a.splice(3, 2) // get the 2 items starting from index 3

// usunięcie elementów i wstawienie nowych
a.splice(2, 3, 2, 'a', 'b') 
//removes 3 items starting from
//index 2, and adds 2 items,
// still starting from index 2
```

**Łączenie tablic**
```
const a = [1, 2]
const b = [3, 4]
a.concat(b) // 1, 2, 3, 4
```

**Wyszukanie konkretnego elementu**
```
a.indexOf() // Returns the index of the first matching item found, or -1 if not found
a.lastIndexOf() // Returns the index of the last matching item found, or -1 if not found

// Returns the first item that returns true. Returns undefined if not found.
a.find((element, index, array) => {
  //return true or false
})

Często używana składnia:
a.find(x => x.id === my_id)

// findIndex returns the index of the first item that returns true, and if not found, it returns undefined
a.findIndex((element, index, array) => {
  //return true or false
})

a.includes(value) // Returns true if a contains value
a.includes(value, i) // Returns true if a contains value after the position i
```

**Pobranie fragmentu tablicy**
```
a.slice()
```

**Sortowanie tablicy**
Sortowanie alfabetyczne
```
const a = [1, 2, 3, 10, 11]
a.sort() //1, 10, 11, 2, 3

const b = [1, 'a', 'Z', 3, 2, 11]
b = a.sort() //1, 11, 2, 3, Z, a
```
Sortowanie wg zdefiniowanej w funkcji logiki
```
const a = [1, 10, 3, 2, 11]
a.sort((a, b) => a - b) //1, 2, 3, 10, 11
```
Odwrócenie tablicy
```
a.reverse()
```

**Konwersja tablicy na string**
```
a.toString()
a.join(', ') // złączenie elementów tablicy za pomocą separatora
```

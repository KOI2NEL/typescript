### if
```
if (condition) {
  statements
}

if (condition) {
  statements
} else {
  statements
}

if (condition) {
  statements
} else if (condition) {
  statements
} else {
  statements
}
```
### switch
```
switch (expression) {
  case expression:
    statements

  case expression:
  case expression:
    statements

  default:
    statements
}
```
### try
```
try {
  statements
} catch (variable) {
  statements
}

try {
  statements
} catch (variable) {
  statements
} finally {
  statements
}
```
***
### for
```
for (initialization; condition; update) {
  statements
}

const list = ['a', 'b', 'c']
for (let i = 0; i < list.length; i++) {
  console.log(list[i]) //value
  console.log(i) //index
}
```
* Można przerwać wykonanie pętli za pomocą słowa `break`
* Można przejść do kolejnej iteracji pętli za pomocą słowa `continue`
### forEach
Dodana w edycji ES5.
```
const list = ['a', 'b', 'c']
list.forEach((item, index) => {
  console.log(item) //value
  console.log(index) //index
})
//index is optional
list.forEach(item => console.log(item))
```
* nie da się przerwać jej wykonania

### do...while
```
do {
  statements
} while (condition);

const list = ['a', 'b', 'c']
let i = 0
do {
  console.log(list[i]) //value
  console.log(i) //index
  i = i + 1
} while (i < list.length)
```
* Można przerwać wykonanie pętli za pomocą słowa `break`
```
do {
  if (something) break
} while (true)
```
* Można przejść do kolejnej iteracji pętli za pomocą słowa `continue`
```
do {
if (something) continue
  //do something else
} while (true)
```

### while
```
while (condition) {
  statements
}

const list = ['a', 'b', 'c']
let i = 0
while (i < list.length) {
  console.log(list[i]) //value
  console.log(i) //index
  i = i + 1
}
```
* Można przerwać wykonanie pętli za pomocą słowa `break`
```
while (true) {
  if (something) break
}
```
* Można przejść do kolejnej iteracji pętli za pomocą słowa `continue`
```
while (true) {
if (something) continue
  //do something else
}
```

### for...in
```
for (let property in object) {
  console.log(property) //property name
  console.log(object[property]) //property value
}
```

### for...of
```
//iterate over the value
for (const value of ['a', 'b', 'c']) {
  console.log(value) //value
}
//get the index as well, using `entries()`
for (const [index, value] of ['a', 'b', 'c'].entries()) {
  console.log(index) //index
  console.log(value) //value
}
```
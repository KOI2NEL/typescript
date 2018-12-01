# Ćwiczenie 1: deklarowanie zmiennych

## Dokumentacja
[Typy zmiennych](https://www.typescriptlang.org/docs/handbook/basic-types.html)

[Deklarowanie zmiennych](https://www.typescriptlang.org/docs/handbook/variable-declarations.html)

## Zadanie

Utworzyć zmienne z określeniem ich typu:

```
var variableA: number = 2;
var variableB: number = 3;
var variableC: number = 4;
```

Utworzyć zmienną z automatycznie nadanym typem:

```
var inferredvariable = 5;
```

Utworzyć zmienną z typem ale bez nadanej wartości

```
var noInitialValue: number;
```

Sprawdzić wynik w konsoli

```
console.log("variableA + variableB + variableC =" + variableA + variableB + variableC);
console.log("inferredvariable = " + inferredvariable);
console.log("noInitialValue = " + noInitialValue);
```

Inne typy

```
var myBool: boolean = true;
var myNumber: number = 5;
var myString: string = 'Bob';

var myAnyString: any = 'Joe';
var myAnyNumber: any = 3;
var myAnyBool: any = false;

console.log(myBool);
console.log(myNumber);
console.log(myString);
console.log(myAnyString);
console.log(myAnyNumber);
console.log(myAnyBool);
```

# Ćwiczenie 2: Enum

## Dokumentacja
[Enum](https://www.typescriptlang.org/docs/handbook/enums.html)

## Zadanie

Utworzyć Enum

```
enum Color { Red, Green, Blue };
```

Przykład użycia

```
var myColor: number = Color.Green;
console.log('myColor = ' + myColor);

var myColor2: string = Color[0];
console.log('myColor2 = ' + myColor2);
```

# Ćwiczenie 3: tablice

## Dokumentacja
[Tablice](https://www.typescriptlang.org/docs/handbook/basic-types.html)

## Zadanie

Sprawdzić 2 sposoby deklarowania tablic o określonym typie

```
// New array
var list1: number[] = [1, 2, 3];
console.log('list1 array = ' + list1);

// results in the same array as the one above.  This is a style preference.
var list2: Array<number> = [1, 2, 3];
console.log('list2 array = ' + list2);
```

Sprawdzić sposób deklarowania tablicy z niewiadomymi typami wartości

```
//Creating an array of type “any”.
var anyList: any[] = [1, true, "three"];
console.log('anyList[] = ' + anyList);
anyList[1] = 100;
console.log('anyList[] = ' + anyList);
```

Sprawdzić sposób tworzenia tablicy o zadeklarowanej długości

```
// Set the length of an array structure to 10.
var list3:string[] = new Array(10);
console.log('list3 = ' + list3);
```

# Ćwiczenie 4: var, let, const

## Dokumentacja
[Deklarowanie zmiennych](https://www.typescriptlang.org/docs/handbook/variable-declarations.html)

## Zadanie

Zadeklarować przykładowe zmienne i stałe

```
var myVar: number = 111;
let myLet: number = 222;
const myConst: number = 333;
```

Zbadać zasięg zmiennej VAR

```
if (true) {
    var myVar: number = 444;
}
console.log('myVar = ' + myVar);
```

Zbadać zasięg zmiennej LET

```
if (true) {
    let myLet: number = 555;
}
console.log('myLet = ' + myLet);
```

Przeprowadzić próbę zmiany wartości stałej

```
myConst = 123;
console.log('myConst = ' + myConst);
```

# Ćwiczenie 5: Union

## Dokumentacja
[Union](https://www.typescriptlang.org/docs/handbook/advanced-types.html)


## Zadanie

Zadeklarować zmienną typu union dla 3 dopuszczalnych typów zmiennych

```
// declare your union type variable for 3 different types.
var myUnionVar: string | number | boolean;
console.log('myUnionVar before setting a value = ' + myUnionVar);

myUnionVar = 5;
console.log('typeof myUnionVar = ' + typeof myUnionVar);
```

Uruchomić przykład i zaobserwować wynik w konsoli

```
var myUnionNumber: number | number[];

myUnionNumber = 100;

if (typeof myUnionNumber === 'number') {
    console.log('myUnionNumber is a number');
}
else {
    console.log('myUnionNumber is now an object');
}

myUnionNumber = [100, 200, 300];

if (typeof myUnionNumber === 'object') {
    console.log('myUnionNumber is now an object');
}
else {
    console.log('myUnionNumber is a number');
}
```

# Ćwiczenie 6: pętle for-in vs for-of

## Dokumentacja
[Iteratory](https://www.typescriptlang.org/docs/handbook/iterators-and-generators.html)

## Zadanie

Uruchomić kod i zaobserwować czym się różnią wyniki poszczególnych iteratorów

```
var items: string[] = ['Bob', 'and', 'Tom'];
console.log('items = ' + items);

// for in loop
for (let item in items) {
    console.log('for in loop: ' + item);
}

// for of loop
for (let item of items) {
    console.log('for of loop: ' + item);
}
```

# Ćwiczenie 7: funkcje

## Dokumentacja
[Funkcje](https://www.typescriptlang.org/docs/handbook/functions.html)

## Zadanie

Utworzyć funkcję i sprawdzić wynik jej wykonania

```
// Create a simple 'add' function.
function add(a: number, b: number): number {
    return a + b;
}
console.log('named function');
console.log('5 + 2 = ' + add(5, 2));
```

Utworzyć analogiczną funkcję anonimową

```
// Create an ananymous 'add' function.
var add2 = function (a: number, b: number): number {
    return a + b;
}
console.log('anonymous function');
console.log('5 + 5 = ' + add2(5, 5));
```

Utworzyć analogiczną funkcję strzałkową

```
// Create a function using the arrow function.
var add3 = (a: number, b: number): number => {
    return a + b;
}
console.log('arrow function');
console.log('10 + 5 = ' + add3(10, 5));
```

Utworzyć funkcję z wymaganymi parametrami
```
var profile = function (fName: string, lName: string, age: number, height: number, weight: number): string {

    // String interpolation
    console.log(`name: ${fName} ${lName} age: ${age} height: ${height} weight: ${weight}`);

    return '';
};
console.log('all parameters are required');
profile('John', 'Smith', 35, 180, 165);
```

Utworzyć funkcję z opcjonalnymi parametrami

```
// Create a function where only fName and lName are required and the rest
// are optional.
var profileWithOptions = function (fName: string, lName: string, age?: number, height?: number, weight?: number): string {

    // String interpolation
    console.log(`name: ${fName} ${lName} age: ${age} height: ${height} weight: ${weight}`);

    return '';
}
console.log('example of optional parameters');
profileWithOptions('John', 'Smith');
```

Utworzyć funkcję z domyślnymi wartościami parametrów

```
// Create function with default parameters.
var profileWithDefaults = function (fName: string, lName: string, age: number = 18, height: number = 150, weight: number = 100): string {

    // String interpolation
    console.log(`name: ${fName} ${lName} age: ${age} height: ${height} weight: ${weight}`);

    return '';
}
console.log('example of default parameters');
profileWithDefaults('John', 'Smith');
```

# Ćwiczenie 8: interpolacja

## Zadanie

Utworzyć kod z klasyczną konkatenacją

```
var firstName: string = 'Bob';
var career: string = 'programmer';
var newString: string = firstName + ' is a ' + career + '.'
console.log('classic string concatination');
console.log(newString);
```

Zastosować interpolację

```
var newInterpString: string = `${firstName} is a ${career}.`;
console.log('string interpolation');
console.log(newInterpString);
```

# Ćwiczenie 9: interfejsy

## Dokumentacja
[Interfejsy](https://www.typescriptlang.org/docs/handbook/interfaces.html)

## Zadanie

Utworzyć zwykłą tablicę

```
var pets: string[] = ['Jasmin', 'Roxie', 'Sally', 'Rush'];
console.log(pets);
```

Utworzyć interfejs

```
interface pet {
    name: string;
    age: number;
    weight: number;
}
```

Utworzyć nową tablicę z typem interfejsu

```
var complexPetsArray: pet[] = [];
```

Dodać do tablicy obiekt z danymi

```
complexPetsArray.push({
    name: 'Jasmin',
    age: 9,
    weight: 55
});
```

Utworzyć nowy obiekt o typie interfejsu i dodać go do tablicy

```
var roxie: pet = {
    name: 'Roxie',
    age: 6,
    weight: 85
}

complexPetsArray.push(roxie);
console.log(complexPetsArray);
```

Utworzyć tablicę o typie interfejsu z 2 obiektami i dodać ją do poprzedniej tablicy

```
var myPets: pet[] = [{ name: 'Sally', age: 18, weight: 85 }, { name: 'Rush', age: 15, weight: 45}];

complexPetsArray.push(myPets);
console.log(complexPetsArray);
```


# Ćwiczenie 10: sortowanie tablicy

## Zadanie

Utworzyć prosty interfejs

```
interface pet {
    name: string;
    age: number;
    weight: number;
}
```

Utworzyć tablicę o typie interfejsu z obiektami

```
var myPets: pet[] = [
    { name: 'Sally', age: 18, weight: 85 },
    { name: 'Jasmine', age: 9, weight: 55 },
    { name: 'Rush', age: 15, weight: 45 },
    { name: 'Roxie', age: 6, weight: 85 }
];
```

Utworzyć funkcję porównującą wiek

```
var compareAge = function (a: pet, b: pet) {
    if (a.age > b.age) { return -1; }
    if (a.age < b.age) {return 1; }
    return 0;
}
```

Wyświetlić posortowaną tablicę

```
console.log(myPets.sort(compareAge));
```

# Ćwiczenie 11: IIFE

## Zadanie

Uruchomić i przeanalizować jak uzycie IIFE chroni globalny zakres zmiennych

```
(function () {
    // Wrap this simple function in IIFE
    function add(a: number, b: number): number {
        return a + b;
    }
    console.log('5 + 2 = ' + add(5, 2));

})();

// add is not recognized here.
//console.log('5 + 2 = ' + add(5, 2));


(function () {
    // Wrap this function in IIFE
    var add2 = function (a: number, b: number): number {
        return a + b;
    }
    console.log('anonymous function');
    console.log('5 + 5 = ' + add2(5, 5));
})();


(function () {
    // Wrap this function in IIFE
    var add3 = (a: number, b: number): number => {
        return a + b;
    }
    console.log('arrow function');
    console.log('10 + 5 = ' + add3(10, 5));

})();


(function () {
    // Wrap this function in IIFE
    var profile = function (fName: string, lName: string, age?: number
        , height?: number, weight?: number): string {

        // String interpolation
        console.log(`name: ${fName} ${lName} age: ${age} height: ${height} weight: ${weight}`);

        return '';
    }
    console.log('all parameters are required');
    profile('John', 'Smith', 35, 180, 165);

})();


(function () {
    // Wrap this function in IIFE
    var profileWithOptions = function (fName: string, lName: string, age?: number
        , height?: number, weight?: number): string {

        // String interpolation
        console.log(`name: ${fName} ${lName} age: ${age} height: ${height} weight: ${weight}`);

        return '';
    }
    console.log('example of optional parameters');
    profileWithOptions('John', 'Smith');
})();


(function () {

    // Wrap this function in IIFE
    var profileWithDefaults = function (fName: string, lName: string, age: number = 18
        , height: number = 150, weight: number = 100): string {

        // String interpolation
        console.log(`name: ${fName} ${lName} age: ${age} height: ${height} weight: ${weight}`);

        return '';
    }
    console.log('example of default parameters');
    profileWithDefaults('John', 'Smith');
})();

(function () {
    // Wrap this function in IIFE
    for (var index: number = 0; index < 10; index++) {
        console.log(index);
    }
})();

(function () {
    // Wrap this function in IIFE
    var myNumber: number = 5;
    for (var multiplier = 1; multiplier <= 10; multiplier++) {
        var result = myNumber * multiplier;

        console.log(`${myNumber} * ${multiplier} = ${result}`);
    }

})();
```

# Ćwiczenie 12: funkcje strzałkowe

## Dokumentacja
[Funkcje](https://www.typescriptlang.org/docs/handbook/functions.html)

## Zadanie

Uruchomić kod i zaobserwować zwracaną wartość

```
(function () {

// Let's get started!
console.log("Let's get started!");

// "this" works differently in different circumstances.
//  In this class "this" works in a way you might now expect.
class employee {
    userId: string;

    displayUserId() {
        setTimeout(function () {
            console.log(`"this.UserId" is: ${this.userId}`);
        }, 1000);
    }
}

// Creating an object of type employee.
var myEmployee = new employee();
myEmployee.userId = 'abc123';

// Calling the displayUserId method.  
// Notice "this.userId" returns "undefined".
myEmployee.displayUserId();

})();
```

Uruchomić kod z zastosowaniem funkcji strzałkowej i zaobserwować zwracaną wartość

```
class employee2 {
    userId: string;

    displayUserId() {
        setTimeout(() => {
            console.log(`"this.UserId" with an arror function is: ${this.userId}`);
        }, 1000);
    }
}

// Creating an object of type employee.
var myEmployee2 = new employee2();
myEmployee2.userId = 'abc123';

// Calling the displayUserId method.  
// Notice "this.userId" returns "abc123".
myEmployee2.displayUserId();
```

# Ćwiczenie 13: klasy

## Dokumentacja
[Klasy](https://www.typescriptlang.org/docs/handbook/classes.html)

## Zadanie

Utworzyć klasę z 3 właściwościami

```
class myBasicClass {
    property1: number;
    property2: string;
    property3: string;
}

var x = new myBasicClass();
x.property1 = 1;
x.property2 = 'hi';
x.property3 = 'number one';

console.log(x);
```

Utworzyć klasę z konstruktorem przyjmującym 2 parametry i funkcją operującą na tych parametrach

```
class Math {
    constructor(a: number, b: number) {
        console.log(`constructor logic: ${(a + b)}`);
    }
    add(a: number, b: number) {
        console.log(`add function: ${(a + b)}`);
    }
}

var y: Math = new Math(5, 5);
y.add(10, 5);
```

Utworzyć klasę z właściwościami i funkcją operującą na nich

```
class Person {
    FirstName: string;
    LastName: string;
    Email: string;
    fullName() { return `${this.FirstName}, ${this.LastName}`}
}


var z: Person = new Person();
z.FirstName = 'Robert';
z.LastName = 'Dunaway';

var fullName = z.fullName();

console.log(`full name is: ${fullName}`);
```


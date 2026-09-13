# QUINT Language Specification

## Overview

QUINT is a statically-typed, general-purpose programming language combining:
- Python-like syntax
- Strong type system with inference
- Multi-paradigm support (OOP, functional, procedural)
- Memory safety
- High performance

## Basic Types

```quint
// Primitives
Number      // 64-bit float
Integer     // 64-bit signed integer
Boolean     // true/false
String      // UTF-8 text
Null        // null value

// Collections
Array<T>    // Dynamic array
Map<K, V>   // Hash map
Set<T>      // Unique values
Tuple       // Fixed-size collection

// Custom types
class, interface, enum, type
```

## Variables and Constants

```quint
// Variable declaration
let x: Number = 10
let name: String = "Alice"

// Type inference
let y = 20  // Inferred as Integer
let z = "hello"  // Inferred as String

// Constants
const PI = 3.14159
const MAX_SIZE: Integer = 1000
```

## Functions

```quint
// Basic function
fn add(a: Number, b: Number) -> Number {
  return a + b
}

// Optional parameters
fn greet(name: String, greeting: String = "Hello") -> String {
  return greeting + ", " + name
}

// Variadic functions
fn sum(...numbers: Number[]) -> Number {
  let result = 0
  for n in numbers {
    result = result + n
  }
  return result
}

// Lambda functions
let square = (x: Number) -> x * x
let numbers = [1, 2, 3, 4, 5]
let squared = numbers.map(square)
```

## Classes and Objects

```quint
class Person {
  name: String
  age: Integer
  
  fn init(name: String, age: Integer) {
    this.name = name
    this.age = age
  }
  
  fn greet() -> String {
    return "Hi, I'm " + this.name
  }
  
  fn birthday() {
    this.age = this.age + 1
  }
}

// Using classes
let person = new Person("Alice", 30)
print(person.greet())
person.birthday()
```

## Control Flow

```quint
// If-else
if x > 10 {
  print("Large")
} else if x > 5 {
  print("Medium")
} else {
  print("Small")
}

// Switch
switch color {
  case "red":
    print("Stop")
  case "yellow":
    print("Caution")
  case "green":
    print("Go")
  default:
    print("Unknown")
}

// Loops
for i in 0..10 {
  print(i)
}

for item in array {
  print(item)
}

while condition {
  // Do something
}

do {
  // Do something
} while condition
```

## Error Handling

```quint
// Try-catch-finally
try {
  let result = risky_operation()
} catch error: Error {
  print("Error: " + error.message)
} finally {
  cleanup()
}

// Throw
throw new Error("Something went wrong")
```

## Imports and Modules

```quint
// Import entire module
import std

// Import specific items
import { Array, Map } from "std/collections"
import MyClass from "./MyModule"

// Named imports
import { greet as sayHello } from "./greetings"

// Export
export class MyClass {
  // ...
}

export fn myFunction() {
  // ...
}
```

## Concurrency

```quint
// Async functions
async fn fetchData(url: String) -> String {
  let response = await http.get(url)
  return response.body
}

// Promises
let promise = Promise.resolve("Hello")
  .then((value) => value + " World")
  .catch((error) => print(error))

// Parallel execution
let results = await Promise.all([
  fetchData("url1"),
  fetchData("url2"),
  fetchData("url3")
])
```

## Generics

```quint
class Box<T> {
  value: T
  
  fn init(value: T) {
    this.value = value
  }
  
  fn getValue() -> T {
    return this.value
  }
}

let intBox = new Box<Integer>(42)
let stringBox = new Box<String>("Hello")
```

## Standard Library Preview

```quint
// I/O
print(value)
readLine() -> String

// Collections
Array.map(), Array.filter(), Array.reduce()
Map.get(), Map.set()
Set.add(), Set.has()

// Math
math.sqrt(), math.sin(), math.cos()
math.max(), math.min(), math.abs()

// Strings
string.length, string.charAt(), string.substring()
string.toUpperCase(), string.toLowerCase()
string.split(), string.join()

// File I/O
fs.read(), fs.write(), fs.delete()
fs.mkdir(), fs.rmdir()

// Web
http.get(), http.post(), http.put(), http.delete()
json.parse(), json.stringify()

// Database
db.connect(), db.query(), db.execute()

// AI
ai.generate(), ai.analyze(), ai.classify()
```

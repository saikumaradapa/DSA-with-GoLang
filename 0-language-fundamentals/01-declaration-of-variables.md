# 📝 Declaration of Variables in Go
In Go, variables can be declared in several ways.
A variable declaration tells the compiler the name, type, and optionally an initial value.

##  1️⃣ var with Explicit Type & Initialization
```go
var x int = 10
```
- Declares x as an int and initializes it with 10.
- Type is explicitly given.

## 2️⃣ var with Type Inference
```go
var y = 20
```
- Type is inferred from the value (int in this case).


## 3️⃣ var with Zero Value
```go
var z int
```
- z is 0 by default (zero value for int).
### Zero values:

- int → 0
- float → 0.0
- string → ""
- bool → false
- pointer, map, slice, interface → nil

## 4️⃣ Short Variable Declaration (:=)
```go
a := 30
name := "Sai"
isReady := true
```
- Type is inferred.
- Can only be used inside functions (not at package level).

## 5️⃣ Multiple Variable Declarations (Same Type)
```go
var m, n int = 1, 2
var p, q int  // zero values: 0, 0
```

## 6️⃣ Multiple Variable Declarations (Different Types)
```go
var i, j, k = 1, "hello", 3.14
```

7️⃣ Grouped Declaration (var block)
```go
var (
userName string = "Sai"
age      int    = 25
isAdmin  bool   = false
)
```
- Useful for organizing related variables.

## 8️⃣ Uninitialized Multiple Variables with Zero Values
```go
var (
firstName string
lastName  string
score     int
)
```
- All variables get their zero value.

## 9️⃣ Constants (Immutable Variables)
```go
const PI = 3.14159
const Greeting string = "Hello, Go!"
```
- Value must be known at compile time.

## 🔟 Variables with Blank Identifier (_)
```go
x, _ := 5, "ignored"
```
- _ discards a value (used when you don’t care about it).

## 1️⃣1️⃣Global Variables
```go
var GlobalCount = 100
```
- Declared outside functions, accessible to the whole package.
- Must use var (short declaration := not allowed).

## 1️⃣2️⃣ Typed and Untyped Constants
```go
const typedConst int = 42
const untypedConst = 42
```
- Untyped constants are more flexible for assignment.
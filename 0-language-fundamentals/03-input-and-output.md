# 📌 Reading Input & Writing Output in Go

---

## 🖨 Printing Output

### 1️⃣ `fmt.Print()`
- Prints without adding a newline at the end.
```go
fmt.Print("Hello")
fmt.Print(" World") // Output: Hello World
```

### 2️⃣ `fmt.Println()`
- Prints with a space between arguments and adds a newline at the end.
```go
fmt.Println("Hello")
fmt.Println("World")
// Output:
// Hello
// World
```

### 3️⃣ `fmt.Printf()` (Formatted Output)
- Prints according to a **format specifier**.
```go
name := "Sai Kumar"
rollno := 21
fmt.Printf("Name: %s, Roll No: %d\n", name, rollno)
// Output: Name: Sai Kumar, Roll No: 21
```

**Common Format Specifiers:**

| Specifier | Meaning            |
|-----------|--------------------|
| `%d`      | Integer            |
| `%f`      | Float (default 6 decimal places) |
| `%.2f`    | Float (2 decimal places) |
| `%s`      | String             |
| `%t`      | Boolean            |
| `%v`      | Default format for any type |
| `%T`      | Type of the variable |
| `%#v`     | Go-syntax representation |

---

## ⌨ Reading Input

### 1️⃣ `fmt.Scan()`
- Reads space-separated input values.
```go
var name string
var rollno int
fmt.Scan(&name, &rollno) // Example Input: Sai Kumar 21
fmt.Println("Name:", name, "Roll No:", rollno)
```

### 2️⃣ `fmt.Scanln()`
- Reads input until a newline (Enter) is encountered.
```go
var name string
fmt.Scanln(&name) // Example Input: Sai Kumar
fmt.Println("Name:", name)
```

### 3️⃣ `fmt.Scanf()` (Formatted Input)
- Reads input according to a **format specifier**.
```go
var name string
var rollno int
fmt.Scanf("%s %d", &name, &rollno) // Example Input: Sai Kumar 21
fmt.Println("Name:", name, "Roll No:", rollno)
```

---

## 📌 Example: Reading and Printing
```go
package main

import "fmt"

func main() {
	var name string
	var rollno int

	fmt.Print("Enter your name: ")
	fmt.Scanln(&name)

	fmt.Print("Enter your roll number: ")
	fmt.Scan(&rollno)

	fmt.Printf("Hello %s, your roll number is %d.\n", name, rollno)
}
```

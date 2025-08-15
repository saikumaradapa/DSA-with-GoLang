# 📝 Data Types in Go
Go is a statically typed language, which means every variable has a type that is known at compile time.  
Types define the kind of data a variable can store.

---

## 1️⃣ Basic/Primitive Data Types

### 🔹 Integer Types
| Type     | Size (bits) | Range                          |
|----------|-------------|--------------------------------|
| int      | 32 or 64    | Platform dependent             |
| int8     | 8           | -128 to 127                    |
| int16    | 16          | -32,768 to 32,767               |
| int32    | 32          | -2,147,483,648 to 2,147,483,647 |
| int64    | 64          | -(2⁶³) to (2⁶³ - 1)             |
| uint     | 32 or 64    | Platform dependent             |
| uint8    | 8           | 0 to 255                       |
| uint16   | 16          | 0 to 65,535                    |
| uint32   | 32          | 0 to 4,294,967,295              |
| uint64   | 64          | 0 to 18,446,744,073,709,551,615 |

- `byte` → alias for `uint8`
- `rune` → alias for `int32` (represents a Unicode code point)

---

### 🔹 Floating-Point Types
| Type     | Size (bits) | Range / Precision     |
|----------|-------------|-----------------------|
| float32  | 32          | ~6-7 decimal digits   |
| float64  | 64          | ~15-16 decimal digits |

---

### 🔹 Complex Types
```go
var c1 complex64  // real and imag parts are float32
var c2 complex128 // real and imag parts are float64
c := complex(5, 7) // 5 + 7i
realPart := real(c)
imagPart := imag(c)
```

---


### 🔹 String

Immutable sequence of bytes (UTF-8 encoded)  
Can contain Unicode characters  
Zero value: `""` (empty string)

**Declaration Example:**
```go
var name string = "Hello"
```

**Common Operations:**
- Concatenation → `str1 + str2`
- Length → `len(str)`
- Indexing (byte access) → `str[i]`
- Substring (using slice syntax) → `str[start:end]`
- Compare → `str1 == str2`, `str1 != str2`
- Contains → `strings.Contains(str, substr)`
- HasPrefix → `strings.HasPrefix(str, prefix)`
- HasSuffix → `strings.HasSuffix(str, suffix)`
- ToUpper → `strings.ToUpper(str)`
- ToLower → `strings.ToLower(str)`
- Trim → `strings.Trim(str, cutset)`
- Split → `strings.Split(str, sep)`
- Join → `strings.Join(slice, sep)`

---

## 2️⃣ Derived / Composite Types

### 🔹Array

Fixed-size sequence of elements of the same type  
Declared with length  
Zero value: all elements are zero values of the type

**Declaration Example:**
```go
var numbers [3]int = [3]int{1, 2, 3}
```

**Common Operations:**
- Length → `len(arr)`
- Index access → `arr[i]`
- Index assignment → `arr[i] = value`
- Iteration → `for i, v := range arr { ... }`
- Copy → `copy(dest, src)`

---

### 🔹Slice

Dynamic, flexible view into an array  
Backed by an underlying array  
Zero value: `nil` (length 0, capacity 0)

**Declaration Example:**
```go
var fruits []string = []string{"apple", "banana", "cherry"}
```

**Common Operations:**
- Length → `len(slice)`
- Capacity → `cap(slice)`
- Append → `append(slice, elem)`
- Slice (sub-slice) → `slice[start:end]`
- Copy → `copy(dest, src)`
- Make new slice → `make([]T, len, cap)`

---

### 🔹Map

Unordered collection of key-value pairs  
Keys must be comparable (`==` operator supported)  
Zero value: `nil` (must be initialized before use)

**Declaration Example:**
```go
var studentAges map[string]int = map[string]int{"Alice": 20, "Bob": 22}
```

**Common Operations:**
- Create → `make(map[KeyType]ValueType)`
- Insert/Update → `map[key] = value`
- Retrieve → `val := map[key]`
- Delete → `delete(map, key)`
- Check existence → `val, exists := map[key]`
- Length → `len(map)`
- Iterate → `for k, v := range map { ... }`

---

### 🔹Struct

Collection of named fields  
Used to group related data  
Zero value: fields are set to their type’s zero value

**Declaration Example:**
```go
type Person struct {
    Name string
    Age  int
}
```

**Common Operations:**
- Declare → `type StructName struct { ... }`
- Initialize → `var s StructName` / `s := StructName{...}`
- Access field → `s.fieldName`
- Update field → `s.fieldName = value`
- Pointer to struct → `&StructName{...}`
- Anonymous fields (embedding) → `type NewStruct struct { EmbeddedStruct }`

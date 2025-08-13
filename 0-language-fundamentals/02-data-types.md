# 📝 Data Types in Go
Go is a statically typed language, which means every variable has a type that is known at compile time.  
Types define the kind of data a variable can store.

---

## 1️⃣ Basic Data Types

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

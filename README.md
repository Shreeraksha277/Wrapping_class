# Java Object Class & Wrapper Classes

## 1. Object Creation

```java
Abc s = new Abc();
```

### Remember:

```text
Abc → Class / Object Type
s   → Reference Variable
new → Creates Object in Heap Memory
Abc() → Constructor
```

### Simple meaning:

> `s` is a reference variable that refers to an `Abc` object created in Heap Memory.

```text
Stack                  Heap

s ─────────────────→  Abc Object
```

---

## 2. Object Creation with Array

```java
Abc s = new Abc(new Integer[5]);
```

### Break it:

```text
Abc
↓
Class / Object Type

s
↓
Reference Variable

new Abc(...)
↓
Creates Abc Object in Heap

Abc(...)
↓
Calls Constructor

new Integer[5]
↓
Creates Integer Array of Size 5
```

### Simple meaning:

> Create an `Abc` object and pass an `Integer` array of size 5 to its constructor.

---

# 3. Why `Object`?

```java
Object a[];
```

We use `Object` mainly for **general-purpose / flexible use**.

Suppose we want our `Abc` class to work with different types:

```text
Integer
Character
String
Float
etc.
```

Instead of creating separate constructors:

```java
Abc(Integer a[])
Abc(Character a[])
Abc(String a[])
Abc(Float a[])
```

we can use **one common constructor**:

```java
Abc(Object a[])
```

Because `Object` is the parent class of reference types.

### Simple idea:

```text
Integer ────┐
Character ──┤
String ─────┼──→ Object
Float ──────┘
              ↓
       One common type
              ↓
       One constructor
```

### Example:

```java
Abc s  = new Abc(new Integer[5]);
Abc s1 = new Abc(new Character[5]);
Abc s2 = new Abc(new String[5]);
```

All can use:

```java
Abc(Object a[])
```

### ⭐ Remember:

> **`Object` is used to make the class more general, so we don't need to create separate constructors for every reference type.**

---

# 4. Primitive vs Wrapper

### Primitive types:

```text
int
char
float
double
boolean
```

### Wrapper classes:

```text
int     → Integer
char    → Character
float   → Float
double  → Double
boolean → Boolean
```

### Why Wrapper Classes?

`Object` works with **objects**, while `int`, `char`, etc. are **primitive types**.

So when a primitive needs to be treated as an object, its wrapper class is used.

---

# 5. Autoboxing

Java automatically converts:

```text
int → Integer
char → Character
```

Example:

```java
Integer x = 10;
```

Here:

```text
10
↓
int
↓
Integer
```

This is called:

> **Autoboxing**

---

# 6. Unboxing

Reverse conversion:

```text
Integer → int
Character → char
```

Example:

```java
Integer x = 10;
int y = x;
```

This is called:

> **Unboxing**

---

# 7. Why `Integer[5]` and Not `int[5]`?

Our constructor is:

```java
Abc(Object a[])
```

So:

```java
new Integer[5]
```

can be passed because:

```text
Integer[] → Object[] ✅
```

But:

```java
new int[5]
```

cannot be passed as `Object[]` because `int` is a primitive type.

### Remember:

```text
Integer[] → Object[] ✅
Character[] → Object[] ✅

int[] → Object[] ❌
char[] → Object[] ❌
```

---

# 8. Important Array Concept

```java
Object[] a = new Integer[5];
```

This is allowed.

But the **actual array is still `Integer[]`**.

```text
Reference type → Object[]
Actual array   → Integer[]
```

Therefore, the array can store only `Integer` objects.

---

# ⭐ Placement Quick Revision

### Object Creation

```java
Abc s = new Abc();
```

```text
Abc  → Class / Object Type
s    → Reference Variable
new  → Creates Object in Heap
Heap → Object is created here
Abc() → Constructor
```

### Why Object?

```text
Object
  ↓
General / Common Type
  ↓
Can work with different reference types
  ↓
Avoids creating separate constructors
```

### Wrapper Classes

```text
int     → Integer
char    → Character
float   → Float
double  → Double
boolean → Boolean
```

### Conversion

```text
Primitive → Wrapper = Autoboxing
Wrapper → Primitive = Unboxing
```

### Array

```text
Integer[] → Object[] ✅
Character[] → Object[] ✅

int[] → Object[] ❌
char[] → Object[] ❌
```

### ⭐ Remember This

> **Class = Type, Variable = Reference, `new` = Creates Object in Heap, Constructor = Initializes Object.**

> **`Object` = General-purpose type used to avoid creating separate constructors for every reference type.**

---
title: "JavaScript Type Coercion for C Programmers"
date: 2024-12-08
---

Learning JavaScript after years of C and Python. Type coercion keeps tripping me up, so here are my notes.

## What I'm used to (C)

In C, types are explicit and conversions are mostly predictable:
```c
int x = 5;
float y = 3.2;
// Explicit cast needed for clarity
int result = (int)(x + y);
```

## JavaScript's "helpful" approach

JavaScript tries to be helpful by converting types automatically. Sometimes this is great, sometimes it's baffling:

```javascript
"5" + 3      // "53" (string concatenation)
"5" - 3      // 2 (numeric subtraction)
"5" * "2"    // 10 (both converted to numbers)
true + true  // 2 (true becomes 1)
```

## What catches me out

**String + anything = string:**
```javascript
let x = 5;
let result = x + " meters";  // "5 meters" (not an error!)
```

**Comparisons are weird:**
```javascript
"2" > "12"   // true (string comparison, lexicographic)
2 > "12"     // false (string converts to number)
"" == 0      // true (empty string is falsy)
"" === 0     // false (strict equality, no coercion)
```

## My rules of thumb

1. **Use `===` not `==`** - Avoid implicit coercion in comparisons
2. **Explicitly convert** - Use `parseInt()`, `parseFloat()`, `String()` when you care
3. **Watch the `+` operator** - It does both addition and concatenation
4. **Test edge cases** - Empty strings, null, undefined all coerce differently

## Coming from Python

Python is more strict than JavaScript but less strict than C. It won't concatenate strings and numbers, which feels more sensible to me:

```python
"5" + 3  # TypeError in Python
         # "53" in JavaScript
```

## Still learning

This is just scratching the surface. JavaScript's type system has more quirks I'm still discovering. The important thing is being aware that coercion is happening.

## Useful resources

- MDN Web Docs on type coercion
- "You Don't Know JS" book series
- Trial and error (lots of it)

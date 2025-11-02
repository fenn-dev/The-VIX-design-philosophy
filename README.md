# <img src="VIX.svg" alt="drawing" width="30"/> The VIX Design Philosophy

## The Goal

The goal of VIX is to establish a new standard for **high-quality, maintainable, and modular modern code**.

Today’s software landscape often settles for mediocrity — systems built for profit over purpose.  
VIX challenges that norm. It aims to create a **modular, user-friendly ecosystem** designed to make technology better, more transparent, and less frustrating.

Too many users today suffer from crashes, errors, poor design, and confusion.  
VIX seeks to eliminate these issues.

The world should be built for the **convenience of people**, not corporate powers.

VIX also prioritizes **user safety and confidentiality**.  
The modern internet is a hostile space — algorithms trade your data for attention and profit.  
**VIX will never participate in such practices.**

Finally, we believe that **servers and systems should be reliable by design**.  
Many of today’s back-end languages are fast but fragile.  
C++ has matured — it should be leveraged wherever possible to ensure both **safety and efficiency**.

It’s better to **crash and recover cleanly** than to **silently leak data** to millions.

## C++

Always use the **latest supported version** of C++ for your compiler — for example, **C++20** or newer.

### Files and Modules

Until `.ixx` files and C++ modules are fully supported across major toolchains, `.ixx` files should be structured to maintain both **IntelliSense compatibility** and **compiler functionality**.

Use the following pattern:

```cpp
#if defined(__INTELLISENSE__)
#include "header.hpp" // For IntelliSense syntax support
#else
import header;        // For actual module compilation
#endif
```

or

```cpp
#if defined(__INTELLISENSE__)
#include "header.ixx" // For IntelliSense syntax support
#else
import header;        // For actual module compilation
#endif
```

## Readability and Code Flow

### Naming conventions
Variables must prioritize readabiliity and understand, so anyone who reads the code, will be able to understand it.
This mean, variables must contain more than one letter. 

---

For private sections classes `private:` use an "_" to emphesize its concealed intent clear and to prevent homonymys in the code.

---

Classes is to be named using PascalCase, this means to capitalize the first letter of each word instead of using _ to seperate them: `MyClass3D`.

---

For interfaces / Interface classes, commonly used for bridging between source code and DLL, SO files. A capitalized I is to be put before the first letter and the name of the class is still to be written in PastcalCase.

---

Constant values are to be written with full capital letters. Such as `PI` which will always be 3.14... no matter what.

---

For file name consistency, it is preffered to use cammelCase names. And to seperate branding from intent, use _: `renderHandler.ixx`, `TheVIXengine_implementation.cpp`.

---

For local variables, use camelCase

---

Hungarian Notation is to be avoided, so things like `int iCount`, `enum eOptions`

### Indentation
> As ***Linus Torvalds*** once famously said,  
> «*If you need more than three levels of indentation, you're screwed anyway, and should fix your program.*»

Indentations should not exceed three levels. However, singular namespaces are not counted toward this rule.

---

### Quick Fails
Failure cases such as early `return`s should appear toward the top of a function to reduce indentation and improve readability.  
You generally want to limit `else` blocks when possible.

---

### Attributes

Using attributes such as:

- `[[unlikely]]`
- `[[nodiscard]]`
- `[[likely]]`
- `[[noreturn]]`

is **mandatory** for both readability and compiler efficiency.

For **quick-fail paths**, a combination of `[[unlikely]]` and `[[noreturn]]` is **strongly recommended**.

---
---

![VIX Logo](VIX.svg)
Created by Sondre Rasmussen

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

is **mandatory** for both readability and compiler efficiency.

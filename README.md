# <img src="VIX.svg" alt="drawing" width="30"/> The VIX Design Philosophy

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

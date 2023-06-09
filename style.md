# Style guide

This guide is not exhaustive at all. It's just some guidelines I've found help write cleaner code for Bukkit/Spigot plugins.
If you want a more exhaustive list, check out [Google's java style](https://google.github.io/styleguide/javaguide.html).

* The contractor always goes at the top of the class
* Private fields should always be above their getter and/or setter
  * There should be no whitespace between the private declaration, getter, and setter (unless it looks bad in that particular case)
* The methods/fields should try to be in chronological order
---
If, for, while, etc. statements should always be as following no matter how small:
```
if (expression) {
    // ...
}
```
with the only exception being:
```
if (!expression) return;
```

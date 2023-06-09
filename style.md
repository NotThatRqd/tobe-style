# Style guide

This guide is not exhaustive at all. It's just some guidelines I've found help write cleaner code for Bukkit/Spigot plugins.
If you want a more exhaustive list, check out [Google's Java style guide](https://google.github.io/styleguide/javaguide.html).

## Classes

- The constructor always goes at the top of the class
- Private fields should always be above their getter and/or setter
    - There should be no whitespace between the private declaration, getter, and setter (unless it looks bad in that particular case)
- The methods/fields should try to be in chronological order

## Braces and "x statement" stuff

Use K&R braces.

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

## Anotations

- Always use `@Override` when overriding a method.
- Always mark parameters as `@Nullable` or `@NotNull`/`@NonNull`[^1]

[^1]: I haven't had the time to research if `@NotNull` or `@NonNull` is better. Currently I just use Intellij's `@NotNull`

---

Here is an example of what you can get using these guidelines:
```java
public class TobeEnemy {
    public TobeEnemy(@NotNull String name, int health) {
        this.name = name + ChatColor.RESET;
        this.health = health;
    }

    private final String name;
    public String getName() {
        return name;
    }

    private int health;
    public int getHealth() {
        return health;
    }
    public void setHealth(int health) {
        this.health = health;
    }
    public void removeHealth(int amount) {
        if (amount < 0) {
            throw new IllegalArgumentException("Cannot remove a negative number of health");
        }
        this.health -= amount;
    }

}
```

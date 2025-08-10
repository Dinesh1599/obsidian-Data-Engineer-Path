| Data Structure        | Key Operations                      | Description / Example                                        |
| --------------------- | ----------------------------------- | ------------------------------------------------------------ |
| **Set** (`{}`)        | `add(x)`                            | Add element → `s.add(4)`                                     |
|                       | `update(iterable)`                  | Add multiple items → `s.update([4, 5])`                      |
|                       | `remove(x)`                         | Remove element (KeyError if missing)                         |
|                       | `discard(x)`                        | Remove if exists (no error)                                  |
|                       | `pop()`                             | Remove & return arbitrary element                            |
|                       | `clear()`                           | Remove all elements                                          |
|                       | `union()` / `                       | `                                                            |
|                       | `intersection()` / `&`              | Common elements                                              |
|                       | `difference()` / `-`                | Elements in set A not in B                                   |
|                       | `issubset()` / `issuperset()`       | Check subset/superset                                        |
| **Frozenset**         | All set **read-only** operations    | Same as `set` without mutating (`add`, `remove` not allowed) |

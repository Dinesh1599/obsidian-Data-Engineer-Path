Key Operations

| Data Structure        | Key Operations                      | Description / Example                                        |
| --------------------- | ----------------------------------- | ------------------------------------------------------------ |
| **List** (`[]`)       | `append(x)`                         | Add item to end → `lst.append(5)`                            |
|                       | `extend(iterable)`                  | Add multiple items → `lst.extend([4, 5])`                    |
|                       | `insert(i, x)`                      | Insert at position → `lst.insert(1, "hello")`                |
|                       | `remove(x)`                         | Remove first occurrence → `lst.remove("hello")`              |
|                       | `pop(i)`                            | Remove & return item (default last) → `lst.pop()`            |
|                       | `index(x)`                          | Return first index of value → `lst.index(3)`                 |
|                       | `count(x)`                          | Count occurrences → `lst.count(2)`                           |
|                       | `sort()` / `sorted()`               | Sort in-place or return sorted copy                          |
|                       | `reverse()`                         | Reverse in-place                                             |
|                       | Slicing `[start:end:step]`          | Extract sublists → `lst[1:4]`                                |

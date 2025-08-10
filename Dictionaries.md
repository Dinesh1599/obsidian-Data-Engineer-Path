| Data Structure        | Key Operations                      | Description / Example                   |
| --------------------- | ----------------------------------- | --------------------------------------- |
| **Dictionary** (`{}`) | `get(key, default)`                 | Safe key lookup → `d.get("name")`       |
|                       | `keys()` / `values()` / `items()`   | Views of keys, values, or pairs         |
|                       | `update({...})`                     | Merge or update mapping                 |
|                       | `pop(key)`                          | Remove & return value                   |
|                       | `popitem()`                         | Remove & return last inserted pair      |
|                       | `setdefault(key, default)`          | Get value, set if missing               |
|                       | `clear()`                           | Remove all items                        |

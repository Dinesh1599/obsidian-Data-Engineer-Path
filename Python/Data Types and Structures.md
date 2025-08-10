- **Primitive Types**:
    
    - Integers (`int`) — `x = 10`
        
    - Floating-point numbers (`float`) — `pi = 3.14`
        
    - [[Strings]] (`str`) — `"Hello World"`
        
    - Booleans (`bool`) — `True`, `False`
        
- **Data Structures**:
    
    - [[List]] — Ordered, mutable: `my_list = [1, 2, 3]`
        
    - **[[Tuples]]** — Ordered, immutable: `coords = (10, 20)`
        
    - **[[Sets]]** — Unordered, unique values: `{1, 2, 3}`
        
    - **[[Dictionaries]]** — Key-value pairs: `{"name": "Dinesh", "age": 25}`
        
- **Conversions**: `list()`, `dict()`, `set()`, `str()`
    
- **Indexing & Slicing**: `my_list[0:3]`

When to use them:

| Data Structure                  | Ordered?                                            | Mutable?                               | Allows Duplicates?          | Access Time                            | Typical Use Cases                                                       | Example                             |
| ------------------------------- | --------------------------------------------------- | -------------------------------------- | --------------------------- | -------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------- |
| **List** (`[]`)                 | ✅ Yes (insertion order preserved)                   | ✅ Yes                                  | ✅ Yes                       | O(1) for index access, O(n) for search | Ordered collections, sequential data processing, batch inserts          | `nums = [1, 2, 3]`                  |
| **Tuple** (`()`)                | ✅ Yes (insertion order preserved)                   | ❌ No (immutable)                       | ✅ Yes                       | O(1) for index access, O(n) for search | Fixed records, dictionary keys, protecting data from modification       | `coords = (10, 20)`                 |
| **Set** (`{}`)                  | ❌ No (unordered)                                    | ✅ Yes                                  | ❌ No (unique elements only) | O(1) average for membership tests      | Removing duplicates, fast lookups, set operations (union, intersection) | `types = {"Fire", "Water"}`         |
| **Frozenset**                   | ❌ No                                                | ❌ No                                   | ❌ No                        | O(1) membership                        | Immutable set (safe for dictionary keys, caching scenarios)             | `fset = frozenset(["a", "b"])`      |
| **Dictionary** (`{key: value}`) | ✅ Yes (insertion order preserved since Python 3.7+) | ✅ Yes (values mutable, keys immutable) | Keys must be unique         | O(1) average for key lookups           | Key-value mappings, configs, indexes, quick joins                       | `user = {"id": 1, "name": "Alice"}` |
| **String** (`"abc"`)            | ✅ Yes                                               | ❌ No                                   | ✅ Yes                       | O(1) index access                      | Immutable text data, parsing, pattern matching                          | `s = "Hello"`                       |


Example Code:
```
# Lists, Tuples, Sets, Dicts, Slicing, Mutability

# Initial Pokémon data: List of tuples (name, [types])
pokemon = [
    ("Pikachu", ["Electric", "Electric"]),   # duplicate type on purpose
    ("Bulbasaur", ["Grass", "Poison"]),
    ("Charmander", ["Fire"]),
]

# Convert list to dict:
# - Keys: Pokémon name
# - Values: list of types (duplicates removed)
# - dict.fromkeys(types) preserves order while removing duplicates
pokedex = {name: list(dict.fromkeys(types)) for name, types in pokemon}

# Access & update:
# - Lists are mutable, so we can append to a type list directly
pokedex["Pikachu"].append("Cute")

# Slicing:
# - Convert dict items to a list, take first two elements
first_two = list(pokedex.items())[:2]

# Tuples are immutable (good for fixed records)
record = ("Squirtle", ("Water",))
# record[1].append("Ice")  # ❌ would fail: tuple is immutable

# Sets:
# - Extract all unique types from the pokedex values
# - Sets are unordered & store unique elements
all_types = {t for types in pokedex.values() for t in types}

print(pokedex)
# {'Pikachu': ['Electric', 'Cute'], 'Bulbasaur': ['Grass', 'Poison'], 'Charmander': ['Fire']}

print(all_types)
# {'Poison', 'Fire', 'Grass', 'Cute', 'Electric'}
```
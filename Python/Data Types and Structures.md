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

# **When to use them:**

| Data Structure                  | Ordered?                                            | Mutable?                               | Allows Duplicates?          | Access Time                            | Typical Use Cases                                                       | Example                             |
| ------------------------------- | --------------------------------------------------- | -------------------------------------- | --------------------------- | -------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------- |
| **List** (`[]`)                 | ✅ Yes (insertion order preserved)                   | ✅ Yes                                  | ✅ Yes                       | O(1) for index access, O(n) for search | Ordered collections, sequential data processing, batch inserts          | `nums = [1, 2, 3]`                  |
| **Tuple** (`()`)                | ✅ Yes (insertion order preserved)                   | ❌ No (immutable)                       | ✅ Yes                       | O(1) for index access, O(n) for search | Fixed records, dictionary keys, protecting data from modification       | `coords = (10, 20)`                 |
| **Set** (`{}`)                  | ❌ No (unordered)                                    | ✅ Yes                                  | ❌ No (unique elements only) | O(1) average for membership tests      | Removing duplicates, fast lookups, set operations (union, intersection) | `types = {"Fire", "Water"}`         |
| **Frozenset**                   | ❌ No                                                | ❌ No                                   | ❌ No                        | O(1) membership                        | Immutable set (safe for dictionary keys, caching scenarios)             | `fset = frozenset(["a", "b"])`      |
| **Dictionary** (`{key: value}`) | ✅ Yes (insertion order preserved since Python 3.7+) | ✅ Yes (values mutable, keys immutable) | Keys must be unique         | O(1) average for key lookups           | Key-value mappings, configs, indexes, quick joins                       | `user = {"id": 1, "name": "Alice"}` |
| **String** (`"abc"`)            | ✅ Yes                                               | ❌ No                                   | ✅ Yes                       | O(1) index access                      | Immutable text data, parsing, pattern matching                          | `s = "Hello"`                       |


Example Code:
```python
# Lists, Tuples, Sets, Dicts, Slicing, Mutability

# Initial Pokémon data: List of tuples (name, [types])
pokemon = [
    ("Pikachu", ["Electric", "Electric"]), # duplicate type on purpose
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



# **PAGE 2 — _Driver Performance Dashboard_**

Complete analytics for each driver.

### 🎯 **Driver KPIs**

- Total Points
    
- Wins
    
- Podiums (position ≤ 3)
    
- Avg Finishing Position
    
- Best Qualifying Position
    
- Overtake Count (grid – finish)
    
- Reliability Score (DNF %)
    

### 📊 **Visuals**

1. **Results Trend (Line Chart)**  
    Position across races.
    
2. **Qualifying vs Race Performance (Scatter)**  
    x = qualifying position  
    y = race finish
    
3. **Position Change Chart (Column)**  
    `(grid_position - position)`
    
4. **Driver Strength Radar Chart**
    
    - Race Pace
        
    - Qualifying
        
    - Pit Stops
        
    - Reliability
        
    - Overtaking
        
5. **Circuit Performance Heatmap**  
    `race_name` vs `position`
    

### 🔍 **Filters**

- Driver
    
- Race
    
- Year
    

---

# 📄 **PAGE 3 — _Constructor Analytics Dashboard_**

### 🎯 **Constructor KPIs**

- Total Constructor Points
    
- Wins
    
- Podiums
    
- Avg Driver Contribution
    
- Avg Pit Stop Time
    
- Reliability (DNFs per constructor)
    

### 📊 **Visuals**

1. **Constructor Points Trend**  
    Total points across races.
    
2. **Driver Contribution Breakdown (Stacked Bar)**  
    Driver → Points.
    
3. **Pit Stop Performance Box Plot**  
    from `fact_pit_stops`.
    
4. **Constructor vs Circuit Performance**  
    Bar chart: avg finishing positions per circuit.
    
5. **Reliability Matrix**  
    Constructor vs DNF Type.
    

### 🔍 **Filters**

- Constructor
    
- Season
    
- Circuit
    

---

# 📄 **PAGE 4 — _Race Day Dashboard_**

Everything about one race.

### 🎯 **Race KPIs**

- Race Winner
    
- Pole Position
    
- Fastest Lap Driver
    
- Total Laps
    
- DNF Count
    

### 📊 **Visuals**

1. **Grid vs Finish Plot (Sankey or Scatter)**  
    Shows movement.
    
2. **Lap Time Evolution (Line Chart)**  
    Driver lap times vs lap number.
    
3. **Pit Stop Timeline (Gantt Style)**  
    driver vs lap.
    
4. **Race Classification Table**  
    driver | constructor | finish | points | time | status
    
5. **Circuit Map with Race Info**
    

### 🔍 **Filters**

- Race
    
- Driver
    
- Constructor
    

---

# 📄 **PAGE 5 — _Qualifying Performance Dashboard_**

### 🎯 **Qualifying KPIs**

- Pole Positions
    
- Avg Qualifying Position
    
- Q1/Q2/Q3 Avg
    
- Improvement (Q1 → Q3 time delta)
    

### 📊 **Visuals**

1. **Qualifying Distribution (Box Plot)**  
    Q1, Q2, Q3.
    
2. **Delta Improvement Bar Chart**  
    Q1 - Q3.
    
3. **Qualifying vs Finishing Scatter**
    
4. **Session Performance Matrix**  
    race | q1 | q2 | q3
    

### 🔍 **Filters**

- Driver
    
- Constructor
    
- Race
    

---

# 📄 **PAGE 6 — _Lap-Time Analytics Dashboard_**

### 🎯 **Lap KPIs**

- Fastest Lap (Milliseconds)
    
- Avg Race Pace
    
- Lap Degradation Rate
    
- Laps Led
    

### 📊 **Visuals**

1. **Fastest Lap Ranking (Bar)**
    
2. **Lap Pace Evolution (Line)**
    
3. **Driver Pace Comparison Overlay**
    
4. **Lap Time Degradation Curve**  
    slope = degradation rate.
    
5. **Segment-Average Pace Table**
    

### 🔍 **Filters**

- Race
    
- Driver
    
- Constructor
    

---

# 📄 **PAGE 7 — _Pit Stop Insights Dashboard_**

### 🎯 **Pit KPIs**

- Best Pit Stop (Fastest)
    
- Avg Pit Time
    
- Number of Stops per Driver
    
- Time Loss to Pit
    

### 📊 **Visuals**

1. **Pit Stop Duration Distribution (Histogram)**
    
2. **Team Pit Performance (Box Plot)**
    
3. **Pit Stop Timeline (Line)**
    
4. **Pit Stop Impact on Position**  
    before vs after.
    

### 🔍 **Filters**

- Constructor
    
- Race
    
- Driver
    

---

# 📄 **PAGE 8 — _DNF / Status Dashboard_**

### 🎯 **DNF KPIs**

- Total DNFs
    
- DNF Rate by Driver
    
- DNF Rate by Constructor
    
- DNF Type Frequency
    

### 📊 **Visuals**

1. **DNF Breakdown (Bar Chart)**  
    status_text from `dim_status`.
    
2. **DNF Heatmap (Circuit vs Count)**
    
3. **Driver Reliability Ranking Table**
    
4. **DNF Trend Over Season (Line)**
    

### 🔍 **Filters**

- Season
    
- Driver
    
- Constructor
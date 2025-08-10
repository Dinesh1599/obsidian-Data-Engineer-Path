- refers to the order in which the instructions or statements in a program are executed
- Basically Conditions for a code
- Mostly of 2 kinds
	- Conditional Statements
		- [[If-Else]]
	-  Looping Statements
		- [[For Loops]]
		- [[while]]
	- Loop Controls
- They can be nested too

Example:
```python

events = [
    {"user_id": 1, "action": "login"},
    {"user_id": 2, "action": "view"},
    {"user_id": 1, "action": "purchase"},
    {"user_id": 3, "action": "view"},
    {"user_id": 4, "action": "logout"},
]

counts = {"view": 0, "purchase": 0, "other": 0}
for e in events:
    action = e["action"]
    if action == "view":
        counts["view"] += 1
        continue  # skip the rest of loop body
    elif action == "purchase":
        counts["purchase"] += 1
    else:
        counts["other"] += 1

    # Early stop example
    if counts["purchase"] >= 1:
        break

print(counts)  # e.g., {'view': 1, 'purchase': 1, 'other': 0}

```
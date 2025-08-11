In data engineering, errors can:
- Break your ETL pipeline.
- Corrupt your data if not handled correctly.
- Cause silent failures that lead to bad business decisions.

**Good error handling** means:

- You catch problems before they crash the program.
- You log them with useful info.
- You either fix/retry or fail gracefully.

Basic Error Handling
```python

try:
    value = int("abc")  # This will fail
except ValueError:
    print("❌ Could not convert to integer.")


```

 Good Practice: Most commonly seen Python exceptions used in Data Engineering:
 
|Exception|Common Cause in Data Engineering|Example| Ideal Fix                                                |
|---|---|---|---|
|**ValueError**|Bad data format when converting between types|`int("abc")` when parsing CSV column| Validate data before conversion, use `try/except`        |
|**TypeError**|Wrong type used in operation|`"abc" + 5` when combining strings/numbers| Convert types (`str()`, `int()`) before operations       |
|**KeyError**|Missing key/column in dictionary or Pandas DataFrame|`row["age"]` when `age` column doesn’t exist| Use `.get()` for dicts or check `if "col" in df.columns` |
|**IndexError**|Index out of range in list or array|`records[10]` when list has only 5 items| Check `len()` before indexing or loop safely             |
|**FileNotFoundError**|File path incorrect or file not yet generated|`open("/data/input.csv")`| Verify file path exists, use `os.path.exists()`          |
|**PermissionError**|No read/write access to file or folder|Writing to `/root/` without permission| Change file permissions or choose allowed directory      |
|**UnicodeDecodeError**|File encoding mismatch|Reading UTF-16 file as UTF-8| Specify encoding: `open(file, encoding="utf-16")`        |
|**ModuleNotFoundError**|Missing Python package|`import pandas` without installing pandas| Install with `pip install package_name`                  |

Commonly Used Error Handling script: (Let's say its for DB connect)

```python

import time

def connect_to_db():
    raise ConnectionError("Database unreachable.")

for attempt in range(3):
    try:
        connect_to_db()
        print("✅ Connected!")
        break
    except ConnectionError as e:
        print(f"Attempt {attempt+1} failed: {e}")
        time.sleep(2)
else:
    print("❌ All retries failed.")


```


Raise: Type your own exception (Basically, custom exceptions)

```python

class DataValidationError(Exception):
    pass

def process_record(record):
    if "id" not in record:
        raise DataValidationError("Missing 'id' in record.")
    print("Record processed.")

try:
    process_record({"name": "Pikachu"})
except DataValidationError as e:
    print(f"❌ Validation failed: {e}")


```

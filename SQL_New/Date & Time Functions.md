### NOW() or GETDATE()
- Gets todays date and time (the date and time during the execution)
- Needs no dependencies, just type in NOW()  

# Other Functions

## Part Extraction
### DAY
-   Return Day from Date
### MONTH
-   Return Month from Date
### YEAR
  - Return Year from Date
### DATEPART or EXTRACT()
- EXTRACT() pulls out specific parts (like year, month, day, hour) from dates and timestamps.

| Part            | What It Returns           | Range              | Example Result |
| --------------- | ------------------------- | ------------------ | -------------- |
| YEAR            | Year                      | Any year           | 2026           |
| MONTH           | Month number              | 1–12               | 1 (January)    |
| DAY             | Day of month              | 1–31               | 29             |
| QUARTER         | Quarter of year           | 1–4                | 1 (Q1)         |
| WEEK            | Week of year              | 1–53               | 5              |
| DOW             | Day of week               | 0–6                | 3 (0=Sunday)   |
| ISODOW          | ISO day of week           | 1–7                | 3 (1=Monday)   |
| DOY             | Day of year               | 1–366              | 29             |
| HOUR            | Hour                      | 0–23               | 14             |
| MINUTE          | Minute                    | 0–59               | 30             |
| SECOND          | Second (with decimals)    | 0–59.999999        | 45.123456      |
| MILLISECOND     | Millisecond part          | 0–999              | 123            |
| MICROSECOND     | Microsecond part          | 0–999999           | 123456         |
| EPOCH           | Unix timestamp            | Seconds since 1970 | 1738155045     |
| TIMEZONE        | Timezone offset (seconds) | -43200 to 50400    | -18000         |
| TIMEZONE_HOUR   | Timezone hours            | -12 to 14          | -5             |
| TIMEZONE_MINUTE | Timezone minutes          | 0–59               | 0              |

### DATENAME
- If you want the Date to return Character value 
### DATETRUNC
### EOMONTH

## Format and Casting
### FORMAT
### CONVERT
### CAST
## Calculations
### DATEADD
### DATEDIFF
## Validation
### ISDATE



Referential Integrity Checks (Cross-table validation)
Business Logic Cleaning (Domain-specific)
Time Parsing and Conversions
Create Standardized Dimensions (dim_drivers, dim_constructors, dim_races)
Build Fact Tables (fact_results, fact_lap_times, fact_sprint_results)
Handle NULL and Missing Values with dbt Macros
Remove Outliers and Invalid Records
Data Type Normalization
Derived Columns (Feature Engineering)


|**Table Name**|**Primary Key**|**Foreign Keys**|**References (Parent Tables)**|**RI Tests Needed?**|
|---|---|---|---|---|
|**circuits**|circuitId|—|—|❌ No|
|**races**|raceId|circuitId|circuits|✅ Yes (1 test)|
|**drivers**|driverId|—|—|❌ No|
|**constructors**|constructorId|—|—|❌ No|
|**status**|statusId|—|—|❌ No|
|**seasons**|year|—|—|❌ No|
|**results**|resultId|raceId, driverId, constructorId, statusId|races, drivers, constructors, status|✅ Yes (4 tests)|
|**sprint_results**|resultId|raceId, driverId, constructorId, statusId|races, drivers, constructors, status|✅ Yes (4 tests)|
|**driver_standings**|driverStandingsId|raceId, driverId|races, drivers|✅ Yes (2 tests)|
|**constructor_results**|constructorResultsId|raceId, constructorId|races, constructors|✅ Yes (2 tests)|
|**constructor_standings**|constructorStandingsId|raceId, constructorId|races, constructors|✅ Yes (2 tests)|
|**qualifying**|qualifyId|raceId, driverId, constructorId|races, drivers, constructors|✅ Yes (3 tests)|
|**lap_times**|(raceId, driverId, lap)|raceId, driverId|races, drivers|✅ Yes (2 tests)|
|**pit_stops**|(raceId, driverId, stop)|raceId, driverId|races, drivers|✅ Yes (2 tests)|
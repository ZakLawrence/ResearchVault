---
tags:
  - SQL
---
#### Dates 
Many [[Database]]s contain information that is stored as a `DATE` or `DATETIME` object. 

The `DATE` format is `YYYY-[M]M-[D]D`, where:
- `YYYY`: four digit year
- `[M]M`: One or two digit month 
- `[D]D`: One or two digit day
so `2019-01-10` is the 10th January 2019. 

A `DATETIME` format is the same but with the time added to the end. 

Often it is useful to work with parts of a `DATE` object, this can be done using the [[Extract]] keyword. 
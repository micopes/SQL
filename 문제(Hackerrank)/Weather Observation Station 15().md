```
select round(LONG_W, 4)
from station
where LAT_N < 137.2345
order by LAT_N desc
limit 1
```

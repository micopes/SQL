```
select round(sum(LAT_N), 4)
from station
where round(LAT_N, 4) > 38.7880 and round(LAT_N, 4) < 137.2345
```

- round(..., 4) 
> 소수 네자리까지 반올림

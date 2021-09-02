```
select round(abs(max(LAT_N)-min(LAT_N))+abs(max(LONG_W)-min(LONG_W)), 4)
from station
```

- round(num, 4) : 소수 넷째자리까지 반올림
- abs
- max
- min

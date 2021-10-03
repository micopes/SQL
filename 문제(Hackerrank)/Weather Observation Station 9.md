```
select distinct(city) from station
where city not regexp '^[aeiou]'
```

## 2번째
```
select distinct(city)
from station
where city not regexp '^[aeiou]'
```

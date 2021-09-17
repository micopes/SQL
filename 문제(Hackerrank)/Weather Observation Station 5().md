```
select city, length(city) from station
order by length(city) asc, city asc
limit 1;

select city, length(city) from station
order by length(city) desc, city desc
limit 1;
```

<hr>

### 2번째

```
select city, length(city)
from station
order by length(city) asc, city asc
limit 1;

select city, length(city)
from station
order by length(city) desc, city desc
limit 1;
```

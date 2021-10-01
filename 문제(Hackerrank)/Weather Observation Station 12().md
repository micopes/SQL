```
select distinct city from station
where 
    city not regexp '^[aeiou]'
    and city not regexp '[aeiou]$'
```
<br>
<hr>

- 이건 왜 안될까?
```
select distinct city from station
where city not regexp ('^[^aeiou]' and '[^aeiou]$')
```

#### 참고할만한 코드
```
select distinct city from station
where
    city regexp '^[^aeiou].*[^aeiou]$'
```

## 두번째

1)

```
select distinct(city)
from station
where city regexp '^[^aeiou]'
    and city regexp '[^aeiou]$'
```

2)

```
select distinct(city)
from station
where city not regexp '^[aeiou]'
    and city not regexp '[aeiou]$'
```

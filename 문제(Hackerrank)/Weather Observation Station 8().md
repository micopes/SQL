```
select distinct(city) from station
where 
    city regexp '^[aeiou]'
    and city regexp '[aeiou]$'
```

- 참고할만한 다른 사람의 코드

```
select distinct(city) from station
where left(city, 1) in ('a', 'e', 'i', 'o', 'u')
where right(city, 1) in ('a', 'e', 'i', 'o', 'u')
```

<br><hr>
- MSSQL에서만 작동하는 코드
```
select distinct(city) from station
where city like '[aeiou]%[aeiou]'
```

- 작동하지 않은 코드
```
select distinct(city) from station
where 
    city regexp '^[aeiou]$'
```

- 이유
![image](https://user-images.githubusercontent.com/43158502/129734095-dc3f39ce-0040-4a60-ae49-22040b136700.png)


<hr>

# second

```
select distinct(city)
from station
where city regexp '^[aeiou]'
    and city regexp '[aeiou]$'
```

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

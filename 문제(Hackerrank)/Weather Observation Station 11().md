```
select distinct city from station
where 
    city not regexp '^[aeiou]'
    or city not regexp '[aeiou]$'
```

#### 참고할만한 코드

```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[^aeiou]|[^aeiou]$';
```
- `대괄호 안의 ^는 not을 의미.`

- **regexp**

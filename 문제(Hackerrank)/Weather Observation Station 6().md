- MSSQL에서는 되지만 MySQL에서는 되지 않는다.

```
select distinct(CITY) from station
where city like '[aeiou]%'
```


- ***like***는 Mysql에서 작동하지 않는 것으로 보인다.
  - 그래서 like 대신에 REGEXP를 사용한다.

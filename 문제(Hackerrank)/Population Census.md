```
select sum(city.population) 
from city, country
where city.countrycode = country.code and continent = 'Asia'
```

- 한 Table에만 존재하는 key 값은 .을 붙여서 앞에 어떤 테이블 소속인지를 붙여줄 필요가 없지만, 그렇지 않은 경우에는 붙여야 한다.

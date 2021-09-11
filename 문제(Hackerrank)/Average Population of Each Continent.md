```
select country.continent, floor(avg(city.population))
from city
inner join country
on city.countrycode = country.code
group by continent
```

- group by 
- A inner join B on ...

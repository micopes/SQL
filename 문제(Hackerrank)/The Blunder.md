```
select ceil(avg(salary) - avg(replace(salary, '0', '')))
from employees
```

- ceil
> 올림

- replace(salary, '0', '')
> salary에서 0을 없앤다.

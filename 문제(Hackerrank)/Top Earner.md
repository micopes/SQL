```
select salary*months as earning, count(salary*months)
from employee
group by salary*months
order by salary*months desc
limit 1;
```

- select에 들어가는 것은 반드시 group by 해줘야 한다.
  - group by를 해야 count를 집계할 수 있다.

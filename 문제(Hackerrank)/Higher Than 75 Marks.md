```
select name from students
where
    marks > 75
order by right(name, 3), id asc
```

```
select name
from students
where marks > 75
order by right(name, 3), ID asc
```

- right(name, 3)

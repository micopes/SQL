```
select animal_id, name, date_format(datetime, '%Y-%m-%d')
from animal_ins
order by animal_id;
```

- date_format으로 쿼리

<hr>

```
select animal_id, name, substring(datetime, 1, 10)
from animal_ins
order by animal_id;
```

```
select animal_id, name, left(datetime, 10)
from animal_ins
order by animal_id;
```

- substring
- left도 사용가능


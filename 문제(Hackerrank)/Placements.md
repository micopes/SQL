```
select S.name
from (students S join friends F on S.id = F.id
      join packages P1 on S.id = P1.id
      join packages P2 on F.friend_id = P2.id)
where P1.salary < P2.salary
order by P2.salary
```

- 여러 개의 `join` 사용
- `join` 한 여러 테이블들의 구성요소 사용
- `using(id)`로 하면 `on S.id = F.id` 대체 가능

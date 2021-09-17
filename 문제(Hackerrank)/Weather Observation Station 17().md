```
SELECT round(LONG_W, 4)
FROM STATION
WHERE LAT_N > 38.7780
ORDER BY LAT_N ASC
LIMIT 1
```

- 최솟값 구할 시 ORDER BY, LIMIT 사용 참고.

<hr>

### 두번째

```
select round(LONG_W, 4)
from station
where LAT_N > 38.7780
order by LAT_N
limit 1;
```

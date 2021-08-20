```
-- pivot
set @D = 0, @P = 0, @S = 0, @A = 0;

-- rownumber 순으로 하면 아래의 order by name에 의해 알파벳 순으로 출력
select min(Doctor), min(Professor), min(Singer), min(Actor)
from ( select case when occupation = 'Doctor' then name end as Doctor,
              case when occupation = 'Professor' then name end as Professor,
              case when occupation = 'Singer' then name end as Singer,
              case when occupation = 'Actor' then name end as Actor,
              case
                when occupation = 'Doctor' then (@D:=@D+1)
                when occupation = 'Professor' then (@P:=@P+1)
                when occupation = 'Singer' then (@S:=@S+1)
                when occupation = 'Actor' then (@A:=@A+1)
                end as rownumber
              from occupations
              order by name
      ) sub
group by rownumber
```
 
    
    



- sub(하위 쿼리)
- `:=`를 사용하는 것
- CASE WHEN ... THEN END
- pivot table을 만들기 위해 `set`을 사용
- group by 

> 참고: https://techblog-history-younghunjo1.tistory.com/159

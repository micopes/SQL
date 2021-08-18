```
select 
    case
        when greatest(a, b, c) >= (a + b + c) - greatest(a, b, c) then "Not A Triangle"
        when a = b and b = c then "Equilateral"
        when a = b or b = c or c = a then "Isosceles"
        else "Scalene"
    end
from triangles
```

- Case
  - when ... then
  - else
  - end

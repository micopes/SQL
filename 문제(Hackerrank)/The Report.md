```
SELECT 
    CASE WHEN G.grade > 7 THEN S.name ELSE NULL END AS NAME,
    G.grade,
    S.marks
FROM students S
JOIN grades G
ON S.marks BETWEEN G.min_mark and G.max_mark
ORDER BY grade DESC, NAME, marks
```

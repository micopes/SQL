```
set @i = 0;
select repeat('* ', @i := @i + 1) from information_schema.tables
where @i < 20
```

- `repeat`
- `@`
- `information_schema.tables`
- `where`
- `:=`

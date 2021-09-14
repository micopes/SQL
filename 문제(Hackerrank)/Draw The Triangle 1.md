```
set @number = 21;
select repeat('* ', @number := @number - 1) from information_schema.tables
```

- `@` 
  - 변수 앞에 @ 기호가 추가되어 @가 user-defined variable를 선언하는 느낌인 듯(없는 변수는 사용자가 정의할 수 없는 시스템 변수),
  - 이 때는 `=`를 사용(**선언**)
- `:=` 
  - **할당** 연산자로 사용
  
- `repeat` : 반복
- `information_schema.tables` : SQL에서 제공하는 default table

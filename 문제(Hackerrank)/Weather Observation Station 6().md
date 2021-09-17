### 1)
```
select distinct(CITY) from station
where city like '[aeiou]%'
```

### 2)
```
select distinct(CITY) from station
where city regexp '^[aeiou]'
```

> 1)은 MSSQL에서는 되지만 MySQL에서는 되지 않는다.
> 
> 2)이 MySQL에서도 실행되는 코드.

<br>
<hr>

- 처음과 끝은 각각 ^과 $로 표현 가능. 
  - 예를 들어서, `'^a'라면, a로 시작하는 패턴. 그리고 'E$'이라면, E로 끝나는 패턴.`
  - 그러면 `'^eat$'은? -> "eat"를 찾으라는 의미. `
  - 추가로 `.은 임의의 문자이므로, '^...$'은, 길이가 3인 문자열이 패턴에 매칭`


mysql에서는 `regexp`로 정규식(특정한 규칙을 가진 문자열의 집합을 표현하는 데 사용하는 형식 언어)을 표현한다.

<hr>

# 2번째

```
select distinct city from station
where city regexp '^[aeiou]'
```

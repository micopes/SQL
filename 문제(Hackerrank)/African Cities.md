```
select city.name from city, country
where code = countrycode and continent = 'Africa'
```

### 서로 다른 3 가지 방법

```
Select City.Name From City Inner Join Country 
On CountryCode = Code
Where Continent = 'Africa';
```

```
Select City.Name From City, Country
Where Code = CountryCode And Continent = 'Africa';
```

```
Select Name From City Where CountryCode In (
    Select Code From Country Where Continent = 'Africa'
);
```

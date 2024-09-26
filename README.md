# DATABASES
## Exercise 2 
### 1:
```
SELECT * FROM goal;
```
<img width="878" alt="ex2 1" src="https://github.com/user-attachments/assets/5ea27fd5-3ab0-4497-949d-db0c2726a509">

###2
```
SELECT name
FROM airport
WHERE iso_country = 'FI';
```

<img width="362" alt="ex2 2" src="https://github.com/user-attachments/assets/269b6132-f5e7-4b5a-8659-987ad93837e3">

###3
```
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name;
```
<img width="834" alt="2 3" src="https://github.com/user-attachments/assets/2b48b9d7-4624-4593-a6ae-766028e33232">


###4
```
SELECT name, type
FROM airport
WHERE iso_country = 'FI'
ORDER BY type, name;

```
<img width="538" alt="2 4" src="https://github.com/user-attachments/assets/03b47339-63c0-41b4-9986-403e4d6416e6">


###5
```
SELECT name
FROM country
WHERE name LIKE 'F%';
```
<img width="292" alt="2 5" src="https://github.com/user-attachments/assets/ee92d7f3-9413-436b-b363-59ac11089408">

###6
```
SELECT name
FROM country
WHERE name LIKE '%F%';
```
<img width="336" alt="2 6" src="https://github.com/user-attachments/assets/638bb855-03a0-4956-89b9-5a27544d8958">


###7
```SELECT location
FROM game
WHERE screen_name = 'Vesa';
```

<img width="323" alt="2 7" src="https://github.com/user-attachments/assets/94b8bf5e-0dfd-47f8-b5dc-c2d33e0ef13f">

###8
```
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';
```

<img width="635" alt="2,8" src="https://github.com/user-attachments/assets/dab484a5-10bb-412d-a174-a8f93d9651b5">

###9
```
SELECT DISTINCT co2_budget FROM game;
```
<img width="485" alt="2 9" src="https://github.com/user-attachments/assets/2cc050b4-afa2-4fa5-89af-6e1f83b1e0d1">

###10
```
SELECT 
       screen_name,
       @ilkkas_budget AS co2_budget,
       co2_consumed,
       (@ilkkas_budget - co2_consumed) AS co2_left
     FROM 
        game
     WHERE 
        screen_name = 'Ilkka';
```

<img width="764" alt="2 10" src="https://github.com/user-attachments/assets/1d91e53c-27e3-457a-be92-c79af080627b">

## Exercise 3
## Exercise 4## Exercise 5## Exercise 6

###1
###2
###3
###4
###5
###6
###7
###8
###9
###10
###11
###12
###4###4###4


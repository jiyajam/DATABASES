# DATABASES
## Exercise 2 
### 1:
```
SELECT * FROM goal;
```
<img width="878" alt="ex2 1" src="https://github.com/user-attachments/assets/5ea27fd5-3ab0-4497-949d-db0c2726a509">

### 2:
```
SELECT name
FROM airport
WHERE iso_country = 'FI';
```

<img width="362" alt="ex2 2" src="https://github.com/user-attachments/assets/269b6132-f5e7-4b5a-8659-987ad93837e3">

### 3:
```
SELECT name FROM airport WHERE iso_country = 'FI' ORDER BY name;
```
<img width="834" alt="2 3" src="https://github.com/user-attachments/assets/2b48b9d7-4624-4593-a6ae-766028e33232">


### 4:
```
SELECT name, type
FROM airport
WHERE iso_country = 'FI'
ORDER BY type, name;

```
<img width="538" alt="2 4" src="https://github.com/user-attachments/assets/03b47339-63c0-41b4-9986-403e4d6416e6">


### 5:
```
SELECT name
FROM country
WHERE name LIKE 'F%';
```
<img width="292" alt="2 5" src="https://github.com/user-attachments/assets/ee92d7f3-9413-436b-b363-59ac11089408">

### 6:
```
SELECT name
FROM country
WHERE name LIKE '%F%';
```
<img width="336" alt="2 6" src="https://github.com/user-attachments/assets/638bb855-03a0-4956-89b9-5a27544d8958">


### 7:
```SELECT location
FROM game
WHERE screen_name = 'Vesa';
```

<img width="323" alt="2 7" src="https://github.com/user-attachments/assets/94b8bf5e-0dfd-47f8-b5dc-c2d33e0ef13f">

### 8:
```
SELECT co2_consumed FROM game WHERE screen_name = 'Ilkka';
```

<img width="635" alt="2,8" src="https://github.com/user-attachments/assets/dab484a5-10bb-412d-a174-a8f93d9651b5">

### 9:
```
SELECT DISTINCT co2_budget FROM game;
```
<img width="485" alt="2 9" src="https://github.com/user-attachments/assets/2cc050b4-afa2-4fa5-89af-6e1f83b1e0d1">

### 10:
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


### 1:
```
SELECT country.name AS "country name", airport.name AS "airport name"
SELECT country.name AS "country name", airport.name AS "airport name"
FROM country
JOIN airport ON airport.iso_country = country.iso_country
WHERE country.name = 'Iceland';

```
<img width="656" alt="3 1" src="https://github.com/user-attachments/assets/4230a384-d52c-429c-823a-03dc0f54be50">


### 2:
```
SELECT airport.name AS "airport name"
FROM airport
JOIN country ON airport.iso_country = country.iso_country
WHERE country.name = 'France' AND airport.type = 'large_airport';
```
<img width="557" alt="3 2" src="https://github.com/user-attachments/assets/40c98e88-d4fa-4a9b-9ef1-4cd169ef0f7c">

```
### 3:
```SELECT country.name AS country_name, airport.name AS airport_name
FROM airport
JOIN country ON airport.iso_country = country.iso_country
WHERE country.continent = 'AN';
```
<img width="817" alt="3 3" src="https://github.com/user-attachments/assets/4ca01479-e9d2-452a-8605-1d64e6fc5a5a">


### 4:
```
SELECT a.elevation_ft
FROM airport AS a
JOIN game AS g ON a.ident = g.location
WHERE g.screen_name = "Heini";
```
<img width="352" alt="3 4" src="https://github.com/user-attachments/assets/dbca3f2d-8db7-42a3-b223-ca3fc22f5742">

### 5:
```
SELECT elevation_ft * 0.3048 AS elevation_m
FROM airport
JOIN game ON airport.ident = game.location
WHERE game.screen_name = 'Heini';
```
<img width="501" alt="3 5" src="https://github.com/user-attachments/assets/dbe9d63a-21e0-4af2-9439-30874512b4a5">


### 6:
```
SELECT airport.name
FROM airport
JOIN game ON airport.ident = game.location
WHERE game.screen_name = 'Ilkka';
```

<img width="396" alt="3 6" src="https://github.com/user-attachments/assets/d2d89361-9057-4537-a795-40ddca5dadc1">

### 7:
```
SELECT country.name
FROM airport
JOIN game ON airport.ident = game.location
JOIN country ON airport.iso_country = country.iso_country
WHERE game.screen_name = "Ilkka";
```
<img width="555" alt="3 7" src="https://github.com/user-attachments/assets/84765b52-c3ab-4e23-8a74-83cb4dda5978">


### 8:
```
SELECT name
FROM goal, goal_reached, game
WHERE game.id = game_id
  AND goal.id = goal_id
  AND screen_name = "Heini";
```
<img width="313" alt="3 8" src="https://github.com/user-attachments/assets/26be6ecb-0a65-4db5-8ac8-43690d264dbe">


### 9;
```
SELECT airport.name
FROM airport
JOIN game ON airport.ident = game.location
JOIN goal_reached ON game.id = goal_reached.game_id
JOIN goal ON goal_reached.goal_id = goal.id
WHERE game.screen_name = "Ilkka" AND goal.name = "CLOUDS";
```
<img width="529" alt="3 9" src="https://github.com/user-attachments/assets/a8e761f9-330a-468b-af88-badf9490cfdc">



### 10:
```
SELECT country.name
FROM country
JOIN airport ON country.iso_country = airport.iso_country
JOIN game ON airport.ident = game.location
JOIN goal_reached ON game.id = goal_reached.game_id
JOIN goal ON goal_reached.goal_id = goal.id
WHERE game.screen_name = "Ilkka" AND goal.name = "CLOUDS";
```
<img width="552" alt="3 10" src="https://github.com/user-attachments/assets/e3a0b3cd-e157-4cac-86ef-2bec7950248a">

## Exercise 4

### 1:
```
```

### 2:
```
```
### 3:
```
```
### 4:
```
```
### 5:
```
```
### 6:
```
```
### 7:
```
```
### 8:
```
```
### 10:
```
```

## Exercise 5

### 1:
```
```

### 2:
```
```
### 3:
```
```
### 4:
```
```
### 5:
```
```
### 6:
```
```
### 7:
```
```
### 8:
```
```
### 10:
```
```
## Exercise 6

### 1:
```
```

### 2:
```
```
### 3:
```
```
### 4:
```
```
### 5:
```
```
### 6:
```
```
### 7:
```
```
### 8:
```
```
### 10:
```
```
## Exercise 7

### 1:
```
```

### 2:
```
```
### 3:
```
```
### 4:
```
```
### 5:
```
```
### 6:
```
```
### 7:
```
```
### 8:
```
```
### 10:
```
```
## Exercise 8

### 1:
```
```

### 2:
```
```
### 3:
```
```
### 4:
```
```
### 5:
```
```
### 6:
```
```
### 7:
```
```
### 8:
```
```
### 10:
```
```

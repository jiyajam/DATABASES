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
SELECT 
    country.name AS "country name", 
    airport.name AS "airport name"
FROM 
    country 
INNER JOIN 
    airport 
ON 
    airport.iso_country = country.iso_country
WHERE 
    country.name = "Finland" 
    AND scheduled_service = "yes";
```
<img width="358" alt="4 1" src="https://github.com/user-attachments/assets/29a29e1c-29cb-4c45-9691-b21a1946ba78">


### 2:
```
SELECT 
    screen_name, 
    airport.name
FROM 
    game 
INNER JOIN 
    airport ON location = ident;
```
<img width="368" alt="4 2" src="https://github.com/user-attachments/assets/35841cc9-c19a-4cdc-bfdf-873b52659a72">

### 3:
```
SELECT 
    game.screen_name AS "screen_name", 
    country.name AS "name"
FROM 
    game 
JOIN 
    airport ON game.location = airport.ident 
JOIN 
    country ON airport.iso_country = country.iso_country;
```
<img width="301" alt="4 3" src="https://github.com/user-attachments/assets/41e74913-d607-4598-9a8b-654f76263320">

### 4:
```
SELECT 
    airport.name AS "name", 
    game.screen_name AS "screen_name"
FROM 
    airport
LEFT JOIN 
    game ON airport.ident = game.location
WHERE 
    airport.name LIKE '%Hels%';
```
<img width="484" alt="4 4" src="https://github.com/user-attachments/assets/ec528946-a908-4542-a9a7-4d544df227f3">

### 5:
```
SELECT 
    goal.name AS "name", 
    game.screen_name AS "screen_name"
FROM 
    goal
LEFT JOIN 
    goal_reached ON goal.id = goal_reached.goal_id
LEFT JOIN 
    game ON goal_reached.game_id = game.id
WHERE 
    goal.name IN ('HOT', 'COLD', '0DEG', '10DEG', '20DEG', 'CLEAR', 'CLOUDS', 'WINDY');
```
<img width="264" alt="4 5" src="https://github.com/user-attachments/assets/7bbca6d3-1913-467c-9cd2-da5f1377a0a3">


## Exercise 5

### 1:
```
SELECT 
    CASE iso_country
        WHEN 'JP' THEN 'Japan'
        ELSE iso_country
    END AS name
FROM airport
WHERE name LIKE 'Satsuma%';

```

<img width="188" alt="5 1" src="https://github.com/user-attachments/assets/66950d8a-bd34-4ae2-981d-00d877cf9e46">

### 2:
```
SELECT name 
     FROM airport 
     WHERE iso_country = 'MC';
```
<img width="320" alt="5 2" src="https://github.com/user-attachments/assets/8f8adc7e-5e7c-48ce-b904-bfe739185d61">

### 3:
```
SELECT DISTINCT game.screen_name
FROM game
JOIN goal_reached ON game.id = goal_reached.game_id
JOIN goal ON goal_reached.goal_id = goal.id
WHERE goal.name = 'CLOUDS';
```
<img width="205" alt="5 3" src="https://github.com/user-attachments/assets/18cedd04-9f8b-48fa-a982-33aacd6c77a2">


### 4:
```
SELECT name
FROM country
WHERE iso_country NOT IN (SELECT DISTINCT iso_country FROM airport);
```
<img width="259" alt="5 4" src="https://github.com/user-attachments/assets/a2a8a039-089e-460f-85f8-f8902b3891f4">

### 5:
```
SELECT goal.name AS "name"
FROM goal
WHERE id NOT IN (
    SELECT goal_reached.goal_id
    FROM goal_reached
    JOIN game ON goal_reached.game_id = game.id
    WHERE game.screen_name = 'Heini'
```
<img width="195" alt="5 5" src="https://github.com/user-attachments/assets/b3e04434-52ac-415f-8807-a34bce81e22c">



## Exercise 6

### 1:
```
SELECT max(elevation_ft)
FROM airport
ORDER BY elevation_ft DESC
LIMIT 1;
```

<img width="184" alt="6 1" src="https://github.com/user-attachments/assets/4f8b0dc2-8a43-49aa-95be-a362096c96f6">


### 2:
```
SELECT continent, COUNT(*) AS "count(*)"
FROM country
GROUP BY continent
ORDER BY continent;

```
<img width="189" alt="6 2" src="https://github.com/user-attachments/assets/e95c6266-7574-4b66-a9e9-d6973ff4e71d">

### 3:
```
SELECT 
    game.screen_name AS "screen_name", 
    COUNT(goal_reached.goal_id) AS "count(*)"
FROM 
    game
LEFT JOIN 
    goal_reached ON game.id = goal_reached.game_id
LEFT JOIN 
    goal ON goal_reached.goal_id = goal.id
WHERE 
    goal.name IN ('HOT', 'COLD', '0DEG', '10DEG', '20DEG', 'CLEAR', 'CLOUDS', 'WINDY') 
GROUP BY  game.screen_name;
```
<img width="215" alt="6 3" src="https://github.com/user-attachments/assets/bbb717a1-be1c-4796-8774-fe6674c549b3">

### 4:
```
SELECT screen_name
FROM game
WHERE co2_consumed = (
    SELECT MIN(co2_consumed) 
    FROM game
);
```
<img width="184" alt="6 4" src="https://github.com/user-attachments/assets/1380ac0a-915b-45b2-b70e-5056d61449e9">

### 5:
```
SELECT country.name AS name, COUNT(*) AS "count(*)" 
FROM airport
JOIN country ON airport.iso_country = country.iso_country 
GROUP BY country.name 
ORDER BY airport_count DESC LIMIT 50;
```
<img width="317" alt="6 5" src="https://github.com/user-attachments/assets/4e845b04-3dff-48bd-8edb-66a31585e65a">

### 6:
```
SELECT country.name
FROM airport, country
WHERE airport.iso_country = country.iso_country
GROUP BY country.iso_country
HAVING COUNT(*) > 1000;
```
<img width="224" alt="6 6" src="https://github.com/user-attachments/assets/37cdb66f-0f32-4e4a-8f14-4a255903ef8a">

### 7:
```
SELECT name
FROM airport
WHERE elevation_ft = (
    SELECT MAX(elevation_ft)
    FROM airport
);
```
<img width="244" alt="6 7" src="https://github.com/user-attachments/assets/fd2f12f9-8171-490c-8df2-68ecb78d29d0">

### 8:
```
SELECT country.name
FROM airport
JOIN country ON airport.iso_country = country.iso_country
WHERE airport.elevation_ft = (
    SELECT MAX(elevation_ft)
    FROM airport
);
```
<img width="185" alt="6 8" src="https://github.com/user-attachments/assets/192c6dda-fb77-433e-a73e-3ffda90824a9">

### 9:
```
SELECT COUNT(*) AS "count(*)"
FROM goal
JOIN goal_reached ON goal.id = goal_reached.goal_id
JOIN game ON goal_reached.game_id = game.id
WHERE game.screen_name = 'Vesa';
```
<img width="179" alt="6 9" src="https://github.com/user-attachments/assets/bb942bd0-1a79-4d46-9aef-21df7170ac42">


### 10:
```
SELECT airport.name AS "name"
FROM airport
ORDER BY ABS(latitude_deg) DESC
LIMIT 1;
```
<img width="266" alt="6 10" src="https://github.com/user-attachments/assets/9250ad79-b031-4dde-b606-33ff457eab87">

## Exercise 7

### 1:
```
UPDATE game 
SET location = (SELECT ident FROM airport WHERE name = 'Nottingham Airport') 
WHERE screen_name = 'Vesa';

-- Step 2: Update Vesa's co2_consumed by increasing it by 500
UPDATE game 
SET co2_consumed = co2_consumed + 500 
WHERE screen_name = 'Vesa' 
AND location = (SELECT ident FROM airport WHERE name = 'Nottingham Airport');
```
<img width="440" alt="7 1" src="https://github.com/user-attachments/assets/b8f03255-140a-454b-a793-1084b5477537">


### 2:
#### b.
```
goal_reached
```
### 3:
```
DELETE FROM goal_reached;
```
<img width="292" alt="7 3" src="https://github.com/user-attachments/assets/5466600a-c633-4d3a-9c3c-f6062b9537e8">


### 4:
```
DELETE FROM game;
```



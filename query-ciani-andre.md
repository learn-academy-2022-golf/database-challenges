Save your queries in a file if you want to keep them for posterity.

WHERE
What is the population of the US? (HINT: 278357000)

SELECT NAME, population
FROM country
WHERE population = 278357000

What is the area of the US? (HINT: 9.36352e+06)

SELECT*
FROM country
WHERE surfacearea = 9.36352e+06

Which countries gained their independence before 1963?

SELECT*
FROM country
WHERE indepyear = 1963

KENYA

List the countries in Africa that have a population smaller than 30,000,000 and a life expectancy of more than 45? (HINT: 37 entries)

SELECT name, continent, lifeexpectancy
FROM country
WHERE population < 30e6 
AND lifeexpectancy > 45
and continent = 'Africa'

Which countries are something like a republic? (HINT: Are there 122 or 143?)

SELECT name, population, governmentform
FROM country
WHERE governmentform
IN ('Republic')

122


Which countries are some kind of republic and achieved independence after 1945? (HINT: 92 entries)


SELECT name, indepyear, governmentform
FROM country
WHERE governmentform
IN ('Republic','Monarchy')
AND indepyear > 1945

**COME BACK TO**


Which countries achieved independence after 1945 and are not some kind of republic? (HINT: 27 entries)

SELECT *      
FROM country
WHERE 
NOT (governmentform = 'Republic')
AND indepyear > 1945

**COME BACK TO**

ORDER BY
Which fifteen countries have the lowest life expectancy? (HINT: starts with Zambia, ends with Sierra Leonne)

SELECT name, lifeexpectancy     
FROM country
ORDER BY lifeexpectancy ASC;


Which fifteen countries have the highest life expectancy? (HINT: starts with Andorra, ends with Spain)

SELECT name, lifeexpectancy     
FROM country
ORDER BY lifeexpectancy DESC;

Which five countries have the lowest population density (density = population / surfacearea)? (HINT: starts with Greenland)

SELECT name, surfacearea, population,
population / surfacearea AS population_density
FROM country
WHERE population != 0
ORDER BY population_density asc

Which countries have the highest population density?(HINT: starts with Macao)

SELECT name, surfacearea, population,
population / surfacearea AS population_density
FROM country
WHERE population != 0
ORDER BY population_density desc

Which is the smallest country by area? (HINT: .4)

SELECT name, surfacearea
FROM country
WHERE surfacearea != 0
ORDER BY surfacearea asc

Which is the smallest country by population? (HINT: 50)?

SELECT name, population
FROM country
WHERE population != 0
ORDER BY population asc

Which is the biggest country by area? (HINT: 1.70754e+07)

SELECT name, surfacearea
FROM country
WHERE surfacearea != 0
ORDER BY surfacearea desc

Which is the biggest country by population? (HINT: 1277558000)

SELECT name, population
FROM country
WHERE population != 0
ORDER BY population desc

Who is the most influential head of state measured by population? (HINT: Jiang Zemin)

SELECT name, headofstate
FROM country
WHERE population != 0
ORDER BY population desc

Subqueries: WITH
Of the countries with the top 10 gnp, which has the smallest population? (HINT: Canada)

WITH populated_countries AS (
	SELECT name, population, gnp
	FROM country
	WHERE population > 0
	AND gnp > 550000
	)
SELECT name, population, gnp
FROM populated_countries
ORDER BY population desc

Of the 10 least populated countries with permament residents (a non-zero population), which has the largest surfacearea? (HINT: Svalbard and Jan Mayen)

WITH populated_countries AS (
	SELECT name, surfacearea, population
	FROM country
	WHERE surfacearea > 0
	AND population > 0
	)
SELECT name, surfacearea, population
FROM populated_countries
ORDER BY population asc

Aggregate Functions: GROUP BY
Which region has the highest average gnp? (HINT: North America)

SELECT region, COUNT(name)
FROM country
WHERE region='North America'
GROUP BY region

Who is the most influential head of state measured by surface area? (HINT: Elisabeth II)




What is the average life expectancy for all continents?



What are the most common forms of government? (HINT: use count(*))
How many countries are in North America?
What is the total population of all continents?
WHERE
What is the population of the US? (HINT: 278357000)

-SELECT name, country, population
-FROM country
-WHERE population = 278357000

What is the area of the US? (HINT: 9.36352e+06)

-SELECT surfacearea
-FROM country
-WHERE population = 278357000

Which countries gained their independence before 1963?

-SELECT name, indepyear
-FROM country
-WHERE indepyear < 1963

List the countries in Africa that have a population smaller than 30,000,000 and a life expectancy of more than 45? (HINT: 37 entries)

-SELECT name, continent, population, lifeexpectancy
-FROM country
-WHERE continent = 'Africa'
-AND population < 30e6
-AND lifeexpectancy > 45

Which countries are something like a republic? (HINT: Are there 122 or 143?)

-SELECT name, governmentform
-FROM country
-WHERE governmentform
-LIKE '%epublic'

Which countries are some kind of republic and achieved independence after 1945? (HINT: 92 entries)

-SELECT name, governmentform, indepyear
-FROM country
-WHERE governmentform
-LIKE '%epublic'
-AND indepyear > 1945

Which countries achieved independence after 1945 and are not some kind of republic? (HINT: 27 entries)

-SELECT name, governmentform, indepyear
-FROM country
-WHERE NOT(governmentform = 'Republic')
-AND NOT(governmentform = 'Federal Republic')
-AND indepyear > 1945

ORDER BY
Which fifteen countries have the lowest life expectancy? (HINT: starts with Zambia, ends with Sierra Leonne)

-SELECT name, lifeexpectancy, country
-FROM country
-WHERE lifeexpectancy IS NOT NULL
-ORDER BY lifeexpectancy
-LIMIT 15

Which fifteen countries have the highest life expectancy? (HINT: starts with Andorra, ends with Spain)

-SELECT name, lifeexpectancy, country
-FROM country
-WHERE lifeexpectancy IS NOT NULL
-ORDER BY lifeexpectancy DESC
-LIMIT 15

Which five countries have the lowest population density (density = population / surfacearea)? (HINT: starts with Greenland)

-SELECT name, population, surfacearea,
-population / surfacearea AS density
-FROM country
-WHERE population > 1
-ORDER BY density
-LIMIT 5

Which countries have the highest population density?(HINT: starts with Macao)

-SELECT name, population, surfacearea,
-population / surfacearea AS density
-FROM country
-WHERE population > 1
-ORDER BY density DESC

Which is the smallest country by area? (HINT: .4)
Which is the smallest country by population? (HINT: 50)?
Which is the biggest country by area? (HINT: 1.70754e+07)
Which is the biggest country by population? (HINT: 1277558000)
Who is the most influential head of state measured by population? (HINT: Jiang Zemin)
Subqueries: WITH
Of the countries with the top 10 gnp, which has the smallest population? (HINT: Canada)
Of the 10 least populated countries with permament residents (a non-zero population), which has the largest surfacearea? (HINT: Svalbard and Jan Mayen)
Aggregate Functions: GROUP BY
Which region has the highest average gnp? (HINT: North America)
Who is the most influential head of state measured by surface area? (HINT: Elisabeth II)
What is the average life expectancy for all continents?
What are the most common forms of government? (HINT: use count(\*))
How many countries are in North America?
What is the total population of all continents?
Stretch Challenges
Which countries have the letter ‘z’ in the name? How many?
Of the smallest 10 countries by area, which has the biggest gnp? (HINT: Macao)
Of the smallest 10 countries by population, which has the biggest per capita gnp?
Of the biggest 10 countries by area, which has the biggest gnp?
Of the biggest 10 countries by population, which has the biggest per capita gnp?
What is the sum of surface area of the 10 biggest countries in the world? The 10 smallest?
What year is this country database from? Cross reference various pieces of information to determine the age of this database.

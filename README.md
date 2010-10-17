# YQL Datatables for The World Bank Data API

First try, not functional!

https://developer.yahoo.com/yql/console/?debug=true

USE "http://github.com/yql/yql-tables/raw/master/google/google.buzz.updates.xml"

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.indicators.xml" AS worldbank.indicators; 
SELECT * FROM worldbank.indicators WHERE country='TUR' AND indicator='BAR.PRM.SCHL.1519'

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.sources.xml" AS worldbank.sources; 
SELECT * FROM worldbank.sources

## worldbank.sources
USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.sources.xml" AS worldbank.sources; 
SELECT name FROM worldbank.sources

SELECT * FROM worldbank.sources WHERE source_id=11

## worldbank.countries

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.countries.xml" AS worldbank.countries; 
SELECT * FROM worldbank.countries

SELECT * FROM worldbank.countries(0,200)

SELECT * FROM worldbank.countries WHERE iso2Code = "GH"



# possible queries

SELECT date,value FROM worldbank.indicators(0,20) WHERE country='TUR' AND indicator='BAR.PRM.SCHL.1519'


select * from worldbank.indicators where indicator='BAR.PRM.SCHL.1519'
http://api.worldbank.org/countries/all/indicators/BAR.PRM.SCHL.1519
http://api.worldbank.org/countries//indicators/BAR.PRM.SCHL.1519

http://api.worldbank.org/indicators
http://api.worldbank.org/indicators


# Return the definition of the indicator SP.POP.TOTL, in this case, total population
http://api.worldbank.org/indicators/SP.POP.TOTL

# Display all indicators for the source: Doing Business
http://api.worldbank.org/source/Doing Business/indicators

http://api.worldbank.org/indicators?source=Doing Business

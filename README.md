# YQL Datatables for the World Bank Data API

First try, not necessarily all functional!

References:

* [http://data.worldbank.org/developers/api-overview](WorldBank Data AP)
* [https://developer.yahoo.com/yql/guide/](YQL Documentation)

## worldbank.sources
USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.sources.xml" AS worldbank.sources; 
SELECT name FROM worldbank.sources

SELECT * FROM worldbank.sources WHERE source_id=11

## worldbank.countries

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.countries.xml" AS worldbank.countries; 
SELECT * FROM worldbank.countries

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.countries.xml" AS worldbank.countries; 
SELECT * FROM worldbank.countries(0,200)

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.countries.xml" AS worldbank.countries; 
SELECT * FROM worldbank.countries WHERE iso2Code = "GH"

## worldbank.topics

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.topics.xml" AS worldbank.topics; 
SELECT * FROM worldbank.topics

## worldbank.indicators

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.indicators.xml" AS worldbank.indicators; 
SELECT * FROM worldbank.indicators

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.indicators.xml" AS worldbank.indicators; 
SELECT * FROM worldbank.indicators WHERE indicator="SP.POP.TOTL"

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.indicators.xml" AS worldbank.indicators; 
SELECT * FROM worldbank.indicators(0,500) WHERE name LIKE "%female%"

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.indicators.xml" AS worldbank.indicators; 
SELECT * FROM worldbank.indicators WHERE source_id="1"

No longer supported by the WB API:

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.indicators.xml" AS worldbank.indicators; 
SELECT * FROM worldbank.indicators WHERE country="GH"

## worldbank.data

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.data.xml" AS worldbank.data; 
SELECT * FROM worldbank.data WHERE indicator = "SP.POP.TOTL"

* all indicator for Ghana starting from year 2000

USE "http://github.com/spier/yql_worldbank/raw/master/worldbank.data.xml" AS worldbank.data; 
SELECT date FROM worldbank.data(0,200) WHERE indicator = "SP.POP.TOTL" AND country="GH" AND from_year="2000"


# Queries currently not supported by these YQL mappings (please let me know if you do them yourself!)
http://api.worldbank.org/countries/DE/indicators/NY.GNP.PCAP.CD?date=1970




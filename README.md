# YQL Datatables for the World Bank Data API

I have created this YQL datatables to make working with the World bank Data API easier. My goal is to use it for some useful application for the [http://appsfordevelopment.challengepost.com/](Apps for Development) content by you may of course use it for different purposes.

The YQL queries listed below have been tried at least once but I am sure that my YQL datatables are not flawless. Please post issues if you find them, contribute to the table mappings, and let me know if your have made YQL mappings for the World Bank Data API yourself!

You can include all these datatables in the YQL console by launching it via this link:
[http://developer.yahoo.com/yql/console/?env=http://github.com/spier/yql_worldbank/raw/master/alltables.env]

Once you have done that, try out any of the YQL queries below

References:

* [http://data.worldbank.org/developers/api-overview](WorldBank Data AP)
* [https://developer.yahoo.com/yql/guide/](YQL Documentation)

## worldbank.sources
* get data of all sources

		SELECT * FROM worldbank.sources
		
* get only data for the source with id 11

		SELECT * FROM worldbank.sources WHERE source_id = 11

## worldbank.countries 
* get data for countries (defaults to 10)

		SELECT * FROM worldbank.countries
		
* get the name of all currently available countries (currently 3101)

		SELECT name FROM worldbank.countries(0, 3101)
		
* get all data for Ghana

		SELECT * FROM worldbank.countries WHERE country_id = "GHA"

## worldbank.topics

* get data of all topics

		SELECT * FROM worldbank.topics
		
* get only data for the topic with id 1

		SELECT * FROM worldbank.topics WHERE topic_id = 1

## worldbank.indicators

* get meta data about indicators (defaults to 10)

		SELECT * FROM worldbank.indicators
		
* get meta data of all available indicators (currently 1901)		

		SELECT * FROM worldbank.indicators(0,1901)
		
* get the meta data for the indicator with id 1

		SELECT * FROM worldbank.indicators WHERE indicator_id = "SP.POP.TOTL"

* get meta data about indicators that contain the word "female" in its name

		SELECT * FROM worldbank.indicators(0,500) WHERE name LIKE "%female%" 

* get meta data about indicators that belong to the source with ID 1

		SELECT * FROM worldbank.indicators(0,100) WHERE source_id="1"

* No longer supported by the WB API:

		SELECT * FROM worldbank.indicators WHERE country="GH"

## worldbank.data

* get data for indicator with ID "SP.POP.TOTL" (This returns the first 10 results only, and we did not specify any country or year, so normally this query is not very useful)

		SELECT * FROM worldbank.data WHERE indicator_id = "SP.POP.TOTL"

* get data for indicator with ID "SP.POP.TOTL" in country Ghana, starting from year 2000 (open end)
 
		SELECT * FROM worldbank.data(0,100) WHERE indicator_id = "SP.POP.TOTL" AND country_id = "GHA" AND from_year = 2000

* get data for indicator with ID "SP.POP.TOTL" in country Ghana, for the years 1980 - 1985

		SELECT * FROM worldbank.data(0,100) WHERE indicator_id = "SP.POP.TOTL" AND country_id = "GHA" AND from_year=1980 AND to_year = 1985

* get only year and value for indicator with ID "SP.POP.TOTL" in country Ghana, for the years 1980 - 1985

		SELECT date,value FROM worldbank.data(0,100) WHERE indicator_id = "SP.POP.TOTL" AND country_id = "GH" AND from_year = 1980 AND to_year = 1985

# More Complex Examples




# Queries currently not supported by these YQL mappings (please let me know if you do them yourself!)
http://api.worldbank.org/countries/DE/indicators/NY.GNP.PCAP.CD?date=1970




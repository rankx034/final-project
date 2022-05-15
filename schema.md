## Delhi Weather Schema
The delhi_weather_cleaned.csv file is our provisional database at this point, containing all data needed for the machine learning model. 

The data structure is the following:
- 80,657 rows and 16 columns
- Each row has a timestamp as its index
- The conds column contains the string value for the description of the weather at that time
- dewptm is the dew point in Celsius
- fog, hail, rain, snow, thunder, and tornado columns are all binary values to show whether or not those weather events took place at the time the data was collected
- hum represents humidity level 
- pressurem represents the barometric pressure in millibars
- tempm is the temperature in Celsius
- vism is the visibility range in kilometers
- wdird is the wind direction in degrees
- wdire is the wind direction in string
- wspdm is the wind speed in kph
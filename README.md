# ASHRAE - Great Energy Predictor III

## Abstract
How much energy will a building consume?
 - Q: How much does it cost to cool a skyscraper in the summer?
- A: A lot! And not just in dollars, but in environmental impact.

Thankfully, significant investments are being made to improve building efficiencies to reduce costs and emissions. So, are the improvements working? That’s where you come in. Current methods of estimation are fragmented and do not scale well. Some assume a specific meter type or don’t work with different building types.

Developing energy savings has two key elements: Forecasting future energy usage without improvements, and forecasting energy use after a specific set of improvements have been implemented, like the installation and purchase of investment-grade meters, whose prices continue to fall. One issue preventing moreaggressive growth of the energy markets are the lack of cost-effective, accurate, and scalable procedures for forecasting energy use.

In this competition, I’ll try to develop accurate predictions of metered building energy usage in the following areas: chilled water, electric, natural gas, hot water, and steam meters. The data comes from over 1,000 buildings over a three-year timeframe.

With better estimates of these energy-saving investments, large scale investors and financial institutions will be more inclined to invest in this area to enable progress in building efficiencies.

Founded in 1894, ASHRAE serves to advance the arts and sciences of heating, ventilation, air conditioning refrigeration and their allied fields. ASHRAE members represent building system design and industrial process professionals around theworld. With over 54,000 members serving in 132 countries, ASHRAE supports research, standards writing, publishing and continuing education - shaping tomorrow’s built environment today.

## Data files
* train.csv
    - building_id - Foreign key for the building metadata.
    - meter - The meter id code. Read as {0: electricity, 1: chilledwater, 2: steam, 3: hotwater}. Not every building has all meter types.
    - timestamp - When the measurement was taken
    - meter_reading - The target variable. Energy consumption in kWh (or equivalent). 
* building_meta.csv
    - site_id - Foreign key for the weather files.
     - building_id - Foreign key for training.csv
    - primary_use - Indicator of the primary category of activities for the building based on EnergyStar property type definitions
    - square_feet - Gross floor area of the building
    - year_built - Year building was opened
    - floor_count - Number of floors of the building
* weather_[train/test].csv 
    - site_id
    - air_temperature - Degrees Celsius
    - cloud_coverage - Portion of the sky covered in clouds, in oktas
    - dew_temperature - Degrees Celsius
    - precip_depth_1_hr - Millimeters
    - sea_level_pressure - Millibar/hectopascals
    - wind_direction - Compass direction (0-360)
    - wind_speed - Meters per second
* test.csv
    - row_id - Row id for your submission file
    - building_id - Building id code
    - meter - The meter id code
    - timestamp - Timestamps for the test data period
## Used libraries

  -  pandas, numpy, os
  - matplotlib.pyplot
  - seaborn
  - OneHotEncoder,LabelEncoder
   - Sequential, Dense, Activation, Flatten , GRU , LSTM
  - train_test_split
  - sklearn.metrics.mean_absolute_error 

## Data preprocessing steps
* Data reading
* Data visualization
* Corrolation visualization
* Removing irrelevent Columns
* Dealing with missing values
* Merge the whole data together
* Dealing with skewed variables
* Label Encoding
* Applying log normalisation to the target variable
* Split data into train and test data


## Modeling Phase
We tryed to build several models (see the code above for more details):
* Fully connected neural network
* recurrent neural network

  
  

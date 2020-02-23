Completed: 10-Sep-2019

# Project: Aggregate and analyze US immigration data, by combining it with airport codes and city demographic.

# Source Datasets
The following 3 of the Udacity provided datasets have been used as source files for this project - 
1. I94 Immigration Data: This data comes from the US National Tourism and Trade Office (https://travel.trade.gov/research/reports/i94/historical/2016.html). A data dictionary is included in the workspace. There's a sample file to set a sense of the data in csv format before reading it all in. The entire dataset will not be used.
2. U.S. City Demographic Data: This data comes from OpenSoft (https://public.opendatasoft.com).
3. Airport Code Table: This is a simple table of airport codes and corresponding cities (https://datahub.io/core/airport-codes#data).

# Setup
These datasets used a lot of codes and abbreviations. So, "codesAndAbbreviations.py" has been created to compile these code and Abbreviations from Udacity and github resources. This will be helpful in doing lookup and join during our ETL process.

# Execution
Execute "Capstone Project.ipynb" line by line to load data into target parquet files.

The project follows the follow steps:
- Step 1: Scope the Project and Gather Data
- Step 2: Explore and Assess the Data
- Step 3: Define the Data Model
- Step 4: Run ETL to Model the Data
- Step 5: Complete Project Write Up
Each of the above steps contains detailed explanation of what that step does along with the code. Just follow along!

## Data Dictionary ##

# Dimension Tables

Airport Data
 * country: string, nullable - 'US' as the country code
 * state: string, nullable - State codes
 * avg_elevation: double, nullable - Average elevation of all airports in a state

Demographic Data
 * State: string, nullable - Full name of the State
 * state_code: string, nullable - State code
 * median_age: double, nullable - Median Age of the people in the State
 * pct_male: double, nullable -  Average percentage of male population in the State
 * pct_female: double, nullable - Average percentage of female population in the State
 * pct_veterans: double, nullable - Average percentage of veterans in the State
 * pct_foreign_born: double, nullable - Average percentage of foreign-born nationals in the State
 * Native_American: double, nullable - Average # of Native Americans in the State
 * Asian: double, nullable - Average # of Asians in the State
 * South_American: double, nullable - Average # of South Americans in the State
 * African: double, nullable - Average # of Africans in the State
 * White: double, nullable - Average # of Whites in the State
 
Immigration Data
 * cicid: double, nullable - System generated ID for each immigrant
 * year: integer, nullable - Year of immigration
 * month: integer, nullable - Month of immigration
 * origin_country: string, nullable - Country of origin
 * i94port: string, nullable - Port of entry (City Code)
 * city_port_name: string, nullable - Port of Entry (Name of the City)
 * state_code: string, nullable - State code
 * dest_state_name: string, nullable - State name

Fact Table
 * year: integer, nullable - Year of immigration
 * imm_month: integer, nullable - Month of immigration
 * imm_origin: string, nullable - Country of origin of the immigrant
 * to_imm_state: string, nullable - State an immigrant landed to
 * to_imm_state_count: long, nullable - # of people immigrated in the State
 * avg_elevation: double, nullable - Average elevation of the airports in the State
 * pct_foreign_born: double, nullable - Average percentage of foreign-born nationals in the State
 * Native_American: double, nullable - Average # of Native Americans in the State
 * Asian: double, nullable - Average # of Asians in the State
 * South_American: double, nullable - Average # of South Americans in the State
 * African: double, nullable - Average # of Africans in the State
 * White: double, nullable - Average # of Whites in the State
 
 References:
 1. https://gist.github.com/rogerallen/1583593
 2. https://kite.com/python/docs/pandas.core.indexes.accessors.DatetimeProperties
 3. Udacity provided materials for the course
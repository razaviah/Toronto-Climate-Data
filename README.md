# Toronto Climate Data Automation Project

## Overview
This project automates the task of downloading and aggregating climate data from the Canadian Climate website. The final output is a single CSV file containing data for specific years and months.

## Features
- **Automated Data Download**: Utilizes shell scripting to download hourly climate data.
- **Data Aggregation**: Uses Python to concatenate multiple data files into a single CSV.
- **GitHub Integration**: All scripts and the final CSV file are version-controlled on GitHub.

## How It Works
1. **Shell Script**: Executes a series of `wget` commands to download climate data for Station ID 48549, for the years 2020 to 2022, and for the month of February.
2. **Python Script**: Utilizes `glob` and `pandas` to merge the downloaded data files.
3. **Final Output**: The aggregated data is saved as `all_years.csv`.

## Usage
Run the shell script to start the data download process. Once completed, execute the Python script to aggregate the data. The final output will be saved as `all_years.csv`.

## Technical Details
- **Shell**: Compatible with `bash` and `zsh`, includes error handling and logging.
- **Python**: Uses `pandas` for data manipulation.

## Example Command
```bash
for year in {2020..2022}; 
do wget --content-disposition "https://climate.weather.gc.ca/climate_data/bulk_data_e.html?format=csv&stationID=48549&Year=${year}&Month=2&Day=14&timeframe=1&submit=Download+Data";
done;

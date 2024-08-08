# Home Sales Analysis using SparkSQL

This project demonstrates the use of Apache SparkSQL to analyze home sales data. The analysis covers key metrics such as average home prices based on different criteria. The project also includes steps for optimizing query performance using caching and partitioning.

## Project Structure

- **Home_Sales.ipynb**: The Jupyter Notebook containing the complete analysis and code.
- **home_sales_revised.csv**: The original dataset used for the analysis.
- **home_sales_parquet**: The directory containing the partitioned Parquet files generated during the analysis.

## Dataset

The dataset used in this project is `home_sales_revised.csv`, which contains information on home sales, including the following fields:
- `id`: Unique identifier for each sale.
- `date`: Date of the sale.
- `price`: Sale price of the home.
- `bedrooms`: Number of bedrooms in the home.
- `bathrooms`: Number of bathrooms in the home.
- `sqft_living`: Square footage of the living space.
- `floors`: Number of floors in the home.
- `view`: View rating of the home.
- `date_built`: Year the home was built.

## Analysis Overview

1. **Initialize Spark Session**: Start by setting up a Spark session to handle the data processing.
2. **Data Loading**: Load the `home_sales_revised.csv` file into a Spark DataFrame.
3. **Temporary Table Creation**: Create a temporary table from the DataFrame for executing SQL queries.
4. **SQL Queries**:
    - Calculate the average price for four-bedroom homes sold each year.
    - Calculate the average price of homes with three bedrooms and three bathrooms for each year built.
    - Calculate the average price of homes with three bedrooms, three bathrooms, two floors, and at least 2,000 square feet for each year built.
    - Determine the average price of a home per view rating for homes priced over $350,000 and measure the runtime of this query.
5. **Caching**: Cache the temporary table and run the query again to compare performance.
6. **Partitioning and Parquet**: Partition the data by the year the home was built and save it as Parquet files.
7. **Parquet Querying**: Load the Parquet data, create a temporary table, and run the query to measure runtime.
8. **Uncaching**: Uncache the table and verify the uncaching.

## Instructions

1. **Clone the Repository**: Clone this repository to your local machine.
   ```bash
   git clone https://github.com/your_username/Home_Sales.git
   cd Home_Sales


# Building an Extract-Transform-Load (ETL) Data Processing Pipeline (Python 3 & PostgreSQL)

## Project Overview
This project uses python (pandas) and SQL to construct an ETL (Extract-Transform-Load) data processing pipeline. Our client is Amazing Prime Video, an online movie retailer. They are sponsoring a data processing "hack-a-thon," where participants will be asked to analyze sample data and predict what movies are likely to become popular. Three datasets are being provided to hack-a-thon analysts: (1) a scrape of Wikipedia that includes movies released since 1990 ('wikipedia-movies.json'); (2) a set of movie ratings data from the Movielands website ('ratings.csv'), and (3) metadata from MovieLens ('movies_metadata.csv'). The company wishes to extract the source data, clean and merge them into a single dataset, and then load the cleaned data into a SQL table. 

To this end, we have been asked to provide the following deliverables:
	<ol>
	<li> *Deliverable 1*: Write an ETL Function using Python to Read in Three Data Files;
	<li> *Deliverable 2*: Extract and Transform the Wikipedia Data;
	<li> *Deliverable 3*: Extract and Transform the Kaggle data;
	<li> *Deliverable 4*: Create the merged dataframe (Movie Database).
	</ol>

## Data & Resources
For this project we used Python 3, using Jupyter Notebooks web interface, with the following python packages (modules):
	<ol>
    <li> JSON (to parse unstructured data from web);
	<li> Pandas (to create DataFrames in Python);
	<li> NumPy (to generate descriptive statics);
	<li> Re (for queries involving Regular Expressions);
	<li> SQL Alchemy (to build SQL query engine in Python);
	<li> Psycopg2 (to build PostgreSQL database); and
	<li> Time (for datetime data type conversion);		
	</ol> 

Three source datasets were provided for this analysis:
    	<ol>
		<li> 'wikipedia-movies.json' (from Wikipedia); 
		<li> 'ratings.csv' (from Kaggle);and
        <li> 'movies_metadata.csv' (from MovieLens)
		</ol>
	</ol>


## Results
The python code to extract, transform, and load data was saved to the following files:
	<ol>
	<li> ETL_function_test.ipynb: Extracts data from the three source data files ('wikipedia-movies.json', 'movies_metadata.csv', and 'ratings.csv');	
	<li> ETL_clean_wiki_movies.ipynb: Transforms the Wikipedia data so it can be merged with Kaggle metadata; and 
	<li> ETL_clean_kaggle_data.ipynb: Transforms the Kaggle metadata and MovieLens rating data, converts the transformed data into separate DataFrames, and merges the three dataframes to create the movies_df DataFrame (database).
	</ol>

*Note*: The datasets for this project are relatively large; they are stored in a Resources/ folder, which has been added to the .gitignore file to pre-empt upload to GitHub.
# Building an Extract-Transform-Load (ETL) Data Processing Pipeline (Python 3 & PostgreSQL)

## Project Overview
This project uses python (pandas) and SQL to construct an ETL (Extract-Transform-Load) data processing pipeline. Our client is Amazing Prime Video, an online movie retailer. They are sponsoring a data processing "hack-a-thon," where participants will be asked to analyze sample data and predict what movies are likely to become popular. Two datasets are being provided to hack-a-thon analysts: (1) a scrape of Wikipedia that includes movies released since 1990 () and (2) a set of movie ratings data from the Movielands website ("Kaggle"). The company wishes to extract data from the two data sources, transform the data -- i.e., clean and merge them into a single dataset, and load the cleaned data into a SQL table. We have been asked to provide the following deliverables:
	<ol>
	<li> *Deliverable 1*: Write an ETL Function to Read Three Data Files;
	<li> *Deliverable 2*: Extract and Transform the Wikipedia Data
	<li> *Deliverable 3*: Extract and Transform the Kaggle data
	<li> *Deliverable 4*: Create the Movie Database
	</ol>

## Resources (Source Data & Analysis Software)
For this project we used the following software:
	<ol>
	<li> PosgreSQL (v. 11), using pgAdmin 4 (v. 6.8) interface; and
    <li> Python 3, using Jupyter Notebooks interface.
	</ol> 

XXX source datasets provided for analysis:
    	<ol>
		<li> 'departments.csv' (); and
        <li> 'dept_emp.csv' ()
		</ol>
	</ol>


## Methods
Quick DBD was used to design the entity relationship database (ERD), and Postgres/pgAdmin was used to create the physical ERD, to import and export data, and to generate the following files:
	<ol>
	<li> A relational database schema ('schema.sql' file);
	<li> A SQL queries ('Employee_Database_Challenge. sql') file, together with the following query results (tabular data, exported to CSV files):
    	<ol>
		<li> A Retirement Titles table (Deliverable #1a: 'retirement_titles.csv'), which meets the following requirements: 
		    <ol> It contains a list of employees who were born between Jan 1, 1952 & Dec 31, 1955;
		    <li> It includes emp_no, first_name, & last_name from the 'Employees' table;
		    <li> Data from the 'Employees' table are joined with title, from_date, & to_date data from the 'Titles' table; and
		    <li> The data are ordered by emp_no.
			</ol> 
		<li> A Unique Titles table (Deliverable #1b: 'unique_titles.csv'), which meets the following requirements: 
		    <ol> It contains a list of current employees together with their most recent titles (DISTINCT ON statement used to filter out duplicate entries);
		    <li> It includes emp_no, first_name, & last_name from the Retirement Titles table (Deliverable #1a);
		    <li> It excludes employees who have already left (filtered on to_date = '9999-01-01'); and
		    <li> It is ordered by emp_no (Ascending) & by to_date (Descending).
			</ol> 
		<li> A Retiring Titles table (Deliverable #1c: 'retiring_titles.csv'), which meets the following requirements: 
		    <ol> It contains a count of employees who are about to retire;
		    <li> Data are grouped by title (referencing the Unique Titles table, Deliverable #1b); and
		    <li> It is ordered by count (Descending).
			</ol> 
		<li> A Mentorship Eligibility table (Deliverable #2: 'mentorship_eligibility.csv'), which meets the following requirements: 
		    <ol> It contains a list of employees who are eligible for the PH Mentorship Program;
		    <li> It includes emp_no, first_name, last_name, and birth_date from the Employees table, from_date and to_date columns from the Department Employee table, and current title (from the Titles table);
		    <li> It is generated using a DISTINCT ON statement to exclude duplicate entries;
		    <li> Data are filtered on to_date to retrieve only current employees and on birth_date to get all employees who were born in 1965; and
		    <li> It is ordered by employee number.
			</ol> 
		</ol>
	</ol>


## Results
The code to generate the database schema was saved to 'schema.sql', and the SQL queries (in 'queries.sql') were saved to 'Employee_Database_Challenge.sql' (in ./Queries). The four tables were exported to .csv files ( in ./Data)/

Results suggest the following conclusions:
	<ol>
	<li> *Conclusion 1*: Approximately 72,500 positions will need to be filled in the next several years, including ~25,000 senior engineers, ~25,000 senior staff ~ 10,000 engineers, and ~7,500 staff;	
	<li> *Conclusion 2*: There is a sufficient number of senior staff to mentor the next generation of employees (~434 current senior staff who are eligible for the mentorship program), but the number of senior engineers (~300 eligible for the mentorship program) could place a strain on current resources (assuming they are more costly to train).
	</ol>

*Note*: The datasets for this project are relatively large; they are stored in a Resources/ folder, which has been added to the .gitignore file to pre-empt upload to GitHub.
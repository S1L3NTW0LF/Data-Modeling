# READ ME
The purpose of this project was to help a startup called Sparkify achieve their analytical goals by helping them understand what their users are listening to. This is done by providing a ETL pipline and a database with a star schema so that it is easy to query the data. The reason a star schema was chosen is because it provides fast aggregations for simple queries. 

## Project Description 
The project takes json logs on user activity from user's app as well as a JSON metadata on the songs on their apps and creates a Postgres database with tables optimized for song play analysis. The project includes creating a database schema and a ETL pipeline. 

#### Database Design 
The project uses a star schema made of one fact table and 4 dimension tables. The fact table in this database is the songplays table and the dimension tables are users, songs, artists, time. The purpose of the songplays table is to provide information on what the users are listening to. The users table provides information on users, the artists table on artists and the time table on the time songs are played.  

#### ETL Process 
The first dataset that will be used to build the database is from the Million Song Dataset. It contains JSON metadata about songs. The files are partitioned by the first three letters of each song's track ID. The second dataset consists of activity log files from a music streaming app. These datasets are read into a pandas dataframe, the appropriate columns are selected and then a SQL query is used to insert the data into a the appropriate table. This process is repeated until all files are inserted into the appropriate tables. 

#### Project Repository Files 
data/log_data: This direcotry contains JSON log files. The information in these files is extracted to populate the songplays table (fact table) and the users, time tables (dimension tables). 

data/song_data: Contains a collection of song JSON files. Use to populate songs and artists table (dimension tables). 

create_tables.py: Python script that creates database and tables used to store the data. 

etl.ipynb: Jupyter Notebook that is used to design the ETL process. 

etl.py: Python script that reads JSON files executes ETL process. 

requirements.txt: List of required python modules for this project. 

sql_queries.py: Python script that defines all SQL statements used in project. 

test.ipynb: Used to test that all code functions properly and it meets requirements. 

#### To Run Project 
1. Run for first 3 cells of etl.ipynb
2. Run test.ipynb to see that ETL process was successful 

NOTE: to see a more indepth view of the ETL process run all cells in the etl.ipynb notebook except the third. 
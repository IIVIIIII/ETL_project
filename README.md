# ETL_project

For this project we used two datasets in csv format: one referring to video game sales (vgsales.csv) and another referring to the earnings of esports players (highest_earning_players.csv). The general intent of this project is to transform these data sets such they can later be evaluated in relation to each other, thus providing insight into a represented game's competitive and casual properties.

The transformation process first involves extracting from each data set only those columns deemed relevant and desireable. For the the Sales data this includes the "Rank", "Name", "NA_Sales", "EU_Sales", "JP_Sales", and "Global_Sales" columns, and for the esports data this incudes the "CurrentHandle", "Game", "TotalUSDPrize", and "Genre" columns. Duplicates are then dropped from from the esport's "CurrentHandle" column and the sale's "Name" column. This "Name" column is then renamed to "Game," so as to be consistent between the two tables, and both "Game" collumns are set to be their respective dataframe's index.

With the transformation complete, a connection is established to a designated postgres relational database and the sales dataframe and esports (called: "players") dataframe are pushed to their corresponding tables of the same name. These dataframes appear as follows:

#### Sales Dataframe
![alt text](https://github.com/IIVIIIII/Esports_ETL/blob/main/photos/final_sales_data.png?raw=true)

#### Players Dataframe
![alt text](https://github.com/IIVIIIII/Esports_ETL/blob/main/photos/final_player_data.png?raw=true)



Tools required:
- Python
- Pandas
- PostgreSQL
- Sqlalchemy
# databaseDesign-NCT
This is the database design of a web application that I am developing now 

Database design of the NCT web and mobile application

(see SpecificationsForNCTApp.doc - bullets 6,7)



1.	Requirements and specifications  
2.	Analysis
3.	Conceptual Design 
4.	Implementation Design 
5.	Physical Schema Design and Optimization



1. Requirements and specifications

The database that will store all the data from the NCT application is called Nct_db and it contains several tables. I am listing the tables contained by Nct_db bellow:

Users table( for login purposes) - stores the firstName, lastName, email, password,* of one unique user.
Authorisation table (still for login purposes) - stores network, network_id as fields for saving the social network from which the user can login (Facebook, Google, Twitter)
Results table (for storing the results from a certain lottery draw) - stores the winning numbers from a certain date
Prizes table (has a prize_id field and a category field) - stores an id for a category of prizes
PrizeCategories table (for storing the category of the prizes) - stores X types of categories of prizes 
CategoriesDetails table (for storing the details of a prize category) - stores the name, number of winners for a specific category, the amount of money won and the value left to won in case the prize hasn't been awarded.


The Nct_db will store all the users that are registering on the NCT application. They can register with e-mail and password, or with their favorite social network (Facebook, Google, Twitter) 

The Nct_db database also stores the results of a certain lottery draw that takes place at a specific date for a unique game. The results are stored in the Results table and the plan is to relate this table properly with the other tables left in the database. 

The application NCT with the help of its database: Nct_db will be able to store the Category of prizes *in a view that contains the tables Prizes & Prize Categories*  that are/aren't won by a certain person at a certain date. Having the Categories_Details table will help a lot the NCT users because they will have a clear evidence of the people that won, they will know the number of winners, the value that they won and if they haven't won that time, the value left to be won.


2. Analysis

A Database Data Set is the Result of analyzing the Information from the Requirements Phase

USERS ( user_id, username, password, email, firstName, lastName ) -- other fields might be needed
AUTHORIZATION ( network, network_id, user_id )  
RESULTS ( result_id, selected_win_no, date, game_id, prize_id )
GAMES ( game_id, prize_id, gameName )
PRIZES ( prize_id, category_id )
PRIZE_CATEGORIES ( category_id, categoryName )
CATEGORIES_DETAILS ( category_id, no_of_winners, value_of_winning, value_left_to_win )
 

3.The conceptual Data Model (ERD) 
https://ibb.co/ix6dxo

The conceptual Data Model (ERD) translated into a 4. logical Schema of the database system 
https://ibb.co/m4pLA8

5. Schema and implementation design -  see sqlFiles from NorocCutine Directory!




Bibliography: 
	https://clearbridgemobile.com/how-to-build-a-mobile-app-requirements-document/
	https://www.linkedin.com/pulse/tutorial-step-database-design-sql-david-mccaldin/
	https://www.w3schools.com/sql/
	http://www2.amk.fi/digma.fi/www.amk.fi/opintojaksot/0303011/1142845462205/1142847802793/1142848508953/1142848642251.html
	https://www.sqlshack.com/creating-using-crud-stored-procedures/


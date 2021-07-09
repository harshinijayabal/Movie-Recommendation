# Movie-Recommendation
To build a movie recommendation mechanism within Netflix; Learn from data and recommend best TV shows to users, based on self &amp; others behaviour 
•	Manipulated, cleaned, and mapped the data to predict the user ratings for films.
•	Recommended movies based on initial user response using collaborative filtering and Pearson’s R correlation. to build a movie recommendation mechanism within Netflix. Learn from data and recommend best TV shows to users, based on self & others behaviour. 
•	The dataset I used here come directly from Netflix. It consists of 4 text data files, each file contains over 20M rows, i.e. over 4K movies and 400K customers. All together over 17K movies and 500K+ customers!
•	One of the major challenges is to get all these data loaded into the Kernel for analysis, I encountered - Kernel running out of memory and tried many different ways of how to do it more efficiently.
Data manipulation - Data loading
•	Movie ID (as first line of each new movie record / file)
•	Customer ID
•	Rating (1 to 5)
•	Date they gave the ratings
There is another file contains the mapping of Movie ID to the movie background like name, year of release, etc
•	Visualizing the data the rating tends to be relatively positive (>3). unhappy customers - just leave instead of making efforts to rate. 
•	Data cleaning Looping through dataframe to add Movie ID column made the Kernel run out of memory as it is too inefficient. I achieved my task by first creating a numpy array with correct length then add the whole array as column into the main dataframe.
•	Data slicing The data set was huge.. I tried many different ways but can't get the Kernel running as intended without memory error. So, I tried to reduce the data volumn by improving the data quality
•	Removed movie with too less reviews (they are relatively not popular)
•	Remove customer who give too less reviews (they are relatively less active)
•	NaN still occupy space(removed ones)
•	Before trimming it was around 24 million
•	After trimming it came to 17million
•	Pivoted the data set to put it in a matrix for recommendation
•	Now map the movie name, year and id file
•	Use collaborative filtering
•	Training dataset- what movies did cust_id=1 liked in the past (rating=5)
•	Get data and now predict which movies cust_id=1 would love to watch.
Recommend with Pearsons' R correlations
The way it works is we use Pearsons' R correlation to measure the linear correlation between review scores of all pairs of movies, then we provide the top 10 movies with highest correlations


## Team Name and Members

Team Name: 21479_2

Team Members:
* [@CarsonHall](https://github.com/carsonehall15/21479)
* [@Jacob Hoover](https://github.com/Jakehoov1/SQLGroupProject2)
* [@Ryan Restino](https://github.com/rrestino/Ryan-Restino-MIST4610-GroupProject2)
* [@Mason Sprinkle](https://github.com/masonSprinkle/21479)
* [@Owen Swonger](https://github.com/ocs08576/21479)


## The Dataset


* [DATA SET](https://www.kaggle.com/datasets/danielgrijalvas/movies)

The data set we chose focuses on the movie industry. It has various quantitative and qualitative attributes. These attributes provided us with knowledge about various aspects of the industry and we then asked two different questions to analyze the data.

    1. In the top 20 countries (based on average scores of 
    movies produced in that country), what is the most popular 
    genre (based on score)?
    2. Of countries from 2000 to present with over ten movies 
    and a top ten average gross revenue per movie, which ten 
    offer the highest return on investment? 

Our data set contains 15 columns

    1. budget: the budget of a movie
    2. company: the production company
    3. country: country of origin
    4. director: the director
    5. genre: main genre of the movie.
    6. gross: revenue of the movie
    7. name: name of the movie
    8. rating: rating of the movie (R, PG, etc.)
    9. released: release date (YYYY-MM-DD)
    10. runtime: duration of the movie
    11. score: IMDb user rating
    12. votes: number of user votes
    13. star: main actor/actress
    14. writer: writer of the movie
    15. year: year of release

Our data set contains 6820 movies (rows), some having all of the attributes and some only containing a few of the attributes


## Question #1: In the top 20 countries (based on average scores of movies produced in that country), what is the most popular genre (based on score)?

This question is relevant to management at the company because it will help them to determine their target audience in each country based on the most popular genre that customers and critics like, as well as how the movies are scoring. This way, management can prioritize these genres and maximize profits in these areas.


    Attributes we used for analysis in Map visualization: 
    1. country
    2. SUM(budget)
    3. year

    Attributes we used for analysis in Avg Score visualization:
    1. country
    2. AVG(score)

    Attributes we used for analysis in Percent of Total Movies by Country visualization:
    1. country
    2. COUNT(name)
    

![App Screenshot](https://raw.githubusercontent.com/carsonehall15/21479/main/Screen%20Shot%202023-04-27%20at%205.17.02%20PM.png)


## Explanation of Question #1
It is worth noting that the U.S and some other large markets are not within the top 20 scores. This is likely due to the fact that while producing a larger number of movies, there will be more variance relating to both high and low scores, ultimately bringing the average down. 

As you can see from our visualizations:
    
    The United States has an average score of 6.257.
    However, the United States also has 71.40% of all 
    movies produced. Because of this massive difference 
    in number of movies, the U.S average will be lower  
    as a result of both good and bad movies being 
    produced.

    Lebanon has the highest average score of 8. Yet they 
    make up 0.01% of all movies produced in this data  
    set.

Understanding this information is important in interpreting the data. However, it is also important to note that although some countries produce less movies, their scores are still valid. 


## Manipulations to Data Set for Question #1

    FAVORITE GENRE BY COUNTRY
    1. Filter Country: We filtered the country by movies with the top 20    
    highest scores

    CALCULATED FIELDS
    1. Number of Movies: We created a calculated field of 
    which is a COUNT of the Name of movies which is the primary 
    key for this data set. 

## Question #2: Of countries from 2000 to present with over ten movies and a top ten average gross revenue per movie, which ten offer the highest return on investment? 

This question would be important for an executive to determine in which country it might be the most profitable to produce a movie within. This identifies movies thats profit has greatly exceeded its budget therefore making up for the costs of producing the movie. Looking at Return on Investment for various projects will allow executives in the future to know what projects to spend time on. 

    Attributes we used for Budget vs. Gross Revenue analysis: 
    1. budget
    2. gross
    3. country
    4. Net
    5. ROI
    6. year 
    7. name

    Attributes we used for Average ROI in biggest markets since 2000:
    1. country
    2. AVG(ROI)
    3. budget
    4. AVG(gross)
    5. Net
    6. year
    7. CNT(name)


![App Screenshot](https://raw.githubusercontent.com/carsonehall15/21479/main/Screen%20Shot%202023-04-27%20at%205.59.17%20PM.png)
## Explanation of Question #2. 

The chart shows that the US, Japan, New Zealand, South Korea, Spain, Australia, United Kingdom, China, Germany, and Hong Kong have high returns on average based on the budgets and Gross revenues of movies within those countries. This data also shows a general trendline for Net with a scatterplot divided by red and blue at an ROI of zero. This shows a couple things one of which is the lower quantity of negative ROI movies as budget increases. Additionally, the trendlines given for each of the countries could be used to predict potential returns for movies created  in these countries. However, some of the smaller countries do have a lower R^2 and a lack of fit for the trendline which would cause their predictions to potentially be erroneous. These could still be potentially viable options for a new movie, but more research would likely be needed. 

## Manipulations to Data Set for Question #2

    AVERAGE ROI ANALYSIS: 
    1. Filter country: Filtered by the condition that the field Name would have 
    count of more than 10 values. 
        This was done to make sure that the countries chosen
        had enough data to form a reasonable average and were   
        not outliers or single movies. 

    2. Filter country: Filtered by top based on average Gross 
        This was done to select the countries that were highest
        grossing. Assuming that gross is the closest predictor  
        of market in this dataset average was chosen over sum
        to include potential markets where there have been high
        grossing movies, but that may not have a high count of 
        movies. 
    3. Filter Year: filtered based on range from 2000 to 2020 
        Filtered to make the data more concise and relevant to
        modern business decisions. Should put more focus on
        emerging markets and filter out some historically large
        markets. 
    4. Filter Budget, Gross, Net on relevant values and no nulls.
        There were a couple Null values in the data set that
        were throwing off calculations using gross and budget.
        This filter was implemented to only count movies where 
        there was a registered gross and budget

    PROFIT RATIO TREND LINE ANALYSIS :
    1. Uses the same filters as the Average ROI chart: 

    CALCULATED FIELDS
    1. NET- calculated field defined by gross-budget 
    2. ROI - calculated field defined by Net/budget presented as a percentage. 

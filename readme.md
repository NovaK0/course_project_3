## DATASET
The dataset for this project is scrapped from ESPNcricinfo and some data is taken from Cricsheet and Cricmetric. The data is publically available. 
## APPROACH
## Predicting highest wicket taker and run scorer of the tournament (Task 1):

### Highest wicket taker:
We began with a cricket player dataset from ESPN Cricinfo that included match information for the player with the most wickets taken in the ICC Men's World Cup 2023.
Source: https://www.espncricinfo.com/records/tournament/bowling-most-wickets-career/icc-cricket-world-cup-2023-24-15338
Initially, we downloaded the data in columns like Player, Span, Mat, Inns, Balls, Overs, Mdns, Runs, Wkts, etc. from espncricinfo.com.
Following that, we preprocessed the data by handling categorical variables and choosing pertinent columns. Next, using past performance, we have predicted player wickets using the Random Forest Regressor. and used TensorFlow and Keras to create an Artificial Neural Network (ANN) for comparison. 
The Mean Squared Error has been our performance metric of choice for training and evaluating models, then generated predictions for the complete dataset after examining the model's performance on the test set. Then, by increasing the 'Wickets' column for each player, I estimated the wicket totals for the next two matches (the semi-final matches) and determined which player on each team was playing at their best.
After that, we have divided the number of actual wickets by the number of expected wickets to get a performance score for each player. After two matches, we have estimated each team's total wicket based on the performance score of their best player.
Finally, we made a comparison between the top player from each of the four semi-final teams and the top player from the entire dataset. And we finally got Mohammed Shami as the most wickets taking player in this World Cup.

### Highest run scorer:
We utilized data from ESPN Cricinfo and Cricmetric to predict the batsman likely to score the most runs in the ICC World Cup 2023.
Source ESPN - https://www.espncricinfo.com/records/tournament/batting-most-runs-career/icc-cricket-world-cup-2023-24-15338
Source Cricmetric - http://www.cricmetric.com/, http://www.cricmetric.com/playerstats.py?player=V+Kohli&role=batsman&format=ODI&groupby=venue&playerStatsFilters=on&start_date=2002-01-01&end_date=2023-11-13&venue=Wankhede&venue=Kolkata&venue=Ahmedabad&venue=Motera&start_over=0&end_over=9999,
Initially, we scraped information from espncricinfo.com, compiling a dataset with columns such as Player, Span, Mat, Inns, NO, Runs, HS, Ave, BF, SR, 100s, 50s, 0s, 4s, 6s, and Team for the top 145 batsmen in the tournament.
Additionally, wee gathered venue-specific performance data from Cricmetric, focusing on players' averages in ODI format at venues like Ahmedabad, Mumbai, and Kolkata. I merged these two datasets and selected the top ten players from the semifinalist teams: India, Australia, New Zealand, and South Africa.
Using a CNN model, we made predictions, with the initial result indicating that R Ravindra would score the most runs.
Subsequently, in another attempt, we excluded venue-related columns, leading the model to predict that Q de Kock would be the leading run-scorer.


## Predicting the finalist teams and players (Task 2):

### For teams
For predicting the finalist teams we have collected the data of last 8 years right from Jan 2015 to data available till date (that is till the last match of the league stage).
The data was available on ESPNcricinfo, additionally we have filtered the data and have kept for only 4 finalist teams for relevancy. Current ICC  rankings are also considered of the said qualified teams.
Also the number of times a team has reached to finals and it's record in finals are considered. We have trained our dataset with three different models.
(1) Random forest : The testing accuracy of random forest is 0.718 that is 71%. Out of the 3 models used it is having the best testing accuracy. The tuned hyperparamters for this are max_depth of 5 and n_estimators = 300.
(2) SGD classifier : It is the second model we have used for training our model using the same dataset and it is having accuracy of 0.564 that is 56%.
(3) CNN :In this model we have used two dense layers with 64 and 32 neurons repectively, the activation function used is relu in dense layer and in output layer it is softmax. the model is trained with 10 epochs. The test accuracy is 0.589 that is 58%.

### For players:
For predicting the playing 11 of the both teamns, player data is collected for the ongoing worldcup from ESPNcicinfo for both batsman and bowlers and probability is calculated on behalf of their performance. Also little bias is added in the manner that
who played the last match assuming that none of the player gets injured.
Model used is CNN.

### Results:
For teams in final: We have predicted our finalist teams with each model and every model is giving the same result that is India and Australia are going to be in the finals.
Predicited playing 11 for India: V Kohli, SS Iyer, KL Rahul, RG Sharma, Shubman Gill, Kuldeep Yadav, JJ Bumrah, RA Jadeja, Mohammed Siraj, Mohammed Shami,SA Yadav 
Predicteed playing 11 for Australia: DA Warner, GJ Maxwell, MR Marsh, SPD Smith, M Labuschagne, A Zampa, PJ Cummins, JP Inglis, JR Hazlewood, MA Starc, TM Head  

## Predicting the Winning teams and players (Task 3):
The dataset used here is also the same as for task 2 and approach is same. We have worked with the same models and have tried with and without using the previous appearances of finals (code not included). Without adding the previous appearances 
the model predicted is India as winner and after adding it the model is predicting Australia as winner.

## Distribution of work:
Task 1 is divided into two parts, predicting highest wicket taker and highest run scorer and everything regarding it datascrapping and collection. This task is carried out by 3 persons. Task 2,3 and API generation is carried out by other 2 members.
Task 2 and 3 is available in the main file.
Task 1 (Highest run scorer) is available in branch "harsh-raval" and task 1 (Highest wicket taker) is available in branch "shubham" and "dhvaghera".

# course_project_3
#Predicting the batsman who will score most runs in the tournament.

I utilized data from ESPN Cricinfo and Cricmetric to predict the batsman likely to score the most runs in the ICC World Cup 2023.

Initially, I scraped information from espncricinfo.com,
compiling a dataset with columns such as 
Player, 
Span,
Mat,
Inns,
NO,
Runs,
HS,
Ave,
BF,
SR, 
100s,
50s,
0s,
4s,
6s,
and Team for the top 145 batsmen in the tournament.

Additionally,
I gathered venue-specific performance data from Cricmetric,
focusing on players' averages in ODI format at venues like Ahmedabad, Mumbai, and Kolkata.
I merged these two datasets and selected the top ten players from the semifinalist teams: India, Australia, New Zealand, and South Africa.

Using a CNN model,
I made predictions,
with the initial result indicating that R Ravindra would score the most runs.

Subsequently, in another attempt, I excluded venue-related columns, leading the model to predict that Q de Kock would be the leading run-scorer.

# Unveiling the Next Tennis Superstars with Machine Leaning

My Motivation?

As a passionate tennis enthusiast, I've long been intrigued by the factors that contribute to a player's success on the court. 
I've often pondered whether there are discernible characteristics or early career indicators that hint at a player's potential 
to become a tennis superstar. This innate curiosity propelled me into the realm of tennis analytics, where I sought to unravel 
the mysteries of identifying promising young talents destined for greatness on the court. 

Purpose & Objectives?

In this project, I aimed to simulate the role of a data scientist for an up-and-coming sportswear brand. The core objective was to determine
the predictive potential of a tennis player's success based on the statistics surrounding their first 50 games of their professional career.

Data Source?

I obtained my dataset from Kaggle (https://www.kaggle.com/datasets/guillemservera/tennis) containing all of the men's professional tennis
in the ATP (Association of Tennis Professionals). In my project, I only incorporated the matches starting from the year 2000, since all 
of the matches from the 20th century had insufficient data for proper analysis.

Data Preprocessing?

The dataset presented a challenging format, with each row representing a unique match. Within each row, statistical information for the 
winner and loser was stored in separate columns, necessitating a dissection of the dataset. To facilitate ease of use, I created player-specific 
dictionaries, showing all the games that each individual player has played throughout their career.

Additionally, the dataset lacked clear indications of a player's first ATP match, prompting the establishment of specific criteria to identify 
such instances. I stipulated that a match would be considered a player's first if they were 25 years old or younger and held a rank exceeding 
500. This criteria enabled the extraction of relevant early-career data for analysis and modeling.

After extracting the first 50 games from each player, I calculated the in-game performance of each player by computing the average 
statistics from their initial 50 career matches. This approach led to the creation of a new comprehensive dataframe, containing the
average statistics of each player.

For feature engineering, I implemented several techniques to enhance the dataset's predictive power. Firstly, I utilized one-hot encoding to
transform categorical variables such as players' hand preferences into numerical representations. Additionally, I engineered a win ratio 
column that gauged the value of a win based on the opponent's ranking, employing a fractional system to accurately reflect the competitiveness
of each match. These strategies enriched the dataset with valuable insights, enabling more robust analyses and model training.

Modeling?

For modeling, I employed binary classification models to forecast the likelihood of tennis players entering the top 25
rankings. Specifically, I explored the efficacy of logistic regression, random forest classification, and XGBoost algorithms in capturing underlying
patterns within the data. To assess the performance of these models, I utilized key evaluation metrics such as the classification report and accuracy
score. Upon evaluating the results, I found that the random forest classifier exhibited the highest prediction accuracy among the models tested. 
Encouraged by these findings, I proceeded to fine-tune the hyperparameters of the random forest classifier to further optimize its performance.

For hyperparameter fine-tuning, I used the following parameters to increase the accuracy of the model:

max_depth: None,
min_samples_leaf: 1,
min_samples_split: 2,
n_estimators: 500,

Unfortunately, the hyperparameter fine-tuning only managed to increase the model's accuracy by 1% (from 88% to 89%).

Conclusive thoughts?

In conclusion, while the model demonstrated high accuracy in predicting players who would not reach the top 25 rankings, it performed poorly in 
identifying those who would actually achieve this milestone, as evidenced by low precision and recall values. This discrepancy can be attributed 
to class imbalance, given the scarcity of players reaching the top 25 in the ATP rankings since 2000. To enhance model accuracy, potential strategies
include expanding the criteria to include players within the top 50 rankings or augmenting the dataset with data from the WTA (Women's Tennis Association)
to increase the minority sample size. These adjustments could lead to more robust predictions and improve the model's effectiveness in identifying future 
tennis superstars.

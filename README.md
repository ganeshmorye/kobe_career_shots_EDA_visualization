# What is Exploratory Data Analysis?
As data scientists, we are often dealing with datasets for which we do not have enough domain knowledge, to begin with. We often employ data visualization methods to understand better the data we are dealing with and investigate and analyze the information contained within that data. This process of understanding the story behind the data is called Exploratory Data Analysis viz EDA. 
One can do EDA for several reasons, such as checking for data consistency, spotting any outliers, investigating the relationship between variables, coming up with a strategy to impute missing data values, discovering patterns, etc. EDA is almost always a prerequisite step before data scientists get into the modeling phase of the project. 
Now that we have a brief understanding of EDA, I will demonstrate how to deploy several visualization tools built-in in Python to derive information within the data. An implicit assumption in this process is that we always do not have enough domain knowledge regarding the dataset.
# Dataset for the Project
Kobe Bryant was drafted into the NBA at the age of 16 and had a long, illustrious career spanning over 20 years, earning the sport's highest accolades. I will use a dataset containing information about the different types of shots attempted by Kobe during his 20-year career. The dataset has 1558 rows and 645 columns. Each row represents a game in his career, and the columns represent different attributes associated with that game, such as opponents, season year, type of shots made, etc.
# Data Dictionary
The following is a subset of specific attributes in the input :
 
 | SHOTS_MADE                        |
|-----------------------------------|
| AWAY_GAME                         |
| SEASON_OPPONENT:atl:1996-97       |
| SEASON:1996-97                    |
| MONTH                             |
| PLAYOFFS                          |
| MEAN_X_POSITION                   |
| MEAN_Y_POSITION                   |
| MEAN_SHOT_DISTANCE                |
| MEAN_SHOT_ANGLE                   |
| SHOT_ZONE_RANGE:16-24_ft.         |
| SHOT_ZONE_BASIC:above_the_break_3 |
| SHOT_ZONE_AREA:back_court(bc)     |
| SHOT_TYPE:2pt_field_goal          |
| COMBINED_SHOT_TYPE:bank_shot      |
| SECONDS_REMAINING                 |
| MINUTES_REMAINING                 |
| PERIOD                            |
| ACTION_TYPE:alley_oop_dunk_shot   |
| SEASON_GAME_NUMBER                |
| CAREER_GAME_NUMBER                |

The primary challenge to preparing the data before I could visualize the various attributes was to convert the data from wide-form format to long-form format for the attribute of interest, primarily using regular expression and other pandas dataframe reshaping methods.

# Visualizations
[NBA Appearances by Kobe Bryant by Opponent](imgs/NBA_Appearances_by_Kobe_Bryant.png)
Kobe Bryant played against 33 different opponents during his career, and he missed most of the games in the 2013-14 season. Some of the teams moved cities, so those appearances show the transition from one team to another. E.g., Vancouver Grizzlies moved from Vancouver to Memphis during the 2000-01 season.

[Different Types of Shots Made](imgs/Shots_Made_by_Kobe_Bryant.png)
There are 57 different types of shots attributes in the dataset. This time-series bubble plot shows the different types of shots made by Kobe in every season.
`jump_shot`, `layup_shot`, `driving_layup_shot` were his favorites. This plot shows that not all the different types of shots were tracked when Kobe started his career.

[Combined Shot Types Made](imgs/Combined_Shots_Took_by_Kobe_Bryant.png)
There are six different types of shots tracked here. These shots are the combination of the different types of shots made. 

[Shot Zone Range](imgs/SHOT_ZONE_RANGE_Took_by_Kobe_Bryant.png)
This discusses the range from where the shot was taken. There are five different zone ranges. He was pretty consistent within 8 to 24 ft range. As expected, very few shots were taken from back of the court range

[Shot Zone Basic](imgs/Shot_Zone_Basic_Kobe_Bryant.png)
This discusses the basketball zone from where the shot was taken. 7 different zones are being tracked. `mid-range`, `restricted_area`, and `above_the_break_3` were his favorites

[Shot Zone Area](imgs/Shot_Zone_Area_Kobe_Bryant.png)
This discusses the six different basketball court areas from which Kobe made his shots. The Center area was his favorite, and he didn't specifically prefer left, or the right sides as the number of the shots he took from both sides are equally distributed.

[Shot Types - Field Goal](imgs/Shot_Type_Kobe_Bryant.png)
The number of shots made with 2-pt and 3pt field goals has remained relatively consistent throughout his career.

[Shots by Opponents](imgs/Shots_by_Opponent.png)
This plot shows the split of Kobe's total shots and shots against all of his opponents during his career. He took the most shots against the San Antonio Spurs, followed by the Portland Trail Blazers. Even though the actual number of shots varies depending on the number of games played against an opponent, the percentage of shots made is fairly consistent against all opponents. The percentage of shots made is in the range of 35-40%.

# Conclusions

We see that data wrangling and a few powerful visualizations can effectively tell a story behind an illustrious and very long successful career.
The associated notebook has more details about the workflow and data wrangling tenchniques used in the EDA process.

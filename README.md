# Fantasy Football Project Part Two

## Installing this requirements text will install all packages needed to run my program
## pip install -r requirements.txt. Python Version 3.9.10 - It is important to use this version of Python because NFL Data Py does not work with newer versions of Python. When running my program in the Jupyter Notebook, I would run each line one at a time because it is much faster this way instead of hitting run all.

# Read in Data

## I read in my data from the NFL Data Py module. This module gave me play by play data from NFL seasons and allowed me to do the analysis I wanted to do. I created two datasets from NFL Data Py. One was the past seasons, this data allowed me to create a model for probability of a touchdown base on passed season. The second dataset was the 2022 NFL season. I then merged the two datasets to allow me to analyze the Expected and Actual Touchdowns from NFL Quarterbacks in the 2022 season.


# Manipulate and Clean Data

## I started out using some keywords to find Quarterback related columns in my dataset. Once I found these, I created a Quarterback dataframe with only the revelent columns to NFL Quarterbacks. I sorted by yardline_100 to find the instances of a passing touchdown from each yardline. I did a groupby with pass_touchdown and yardline_100 and got the value counts to create a new qb_prob dataframe. The purpose of this dataframe is to give me the probability of a passing touchdown from each yardline. Once I get this dataframe, I realize that I have the probability of not scoring a passing touchdown but I don't want this so I drop any value that equals zero meaning no passing touchdown. Now, I'm ready to Merge my data with the 2022 NFL Season data. Once, I do this I have a little more clean up to do. I rename several of the columns to make them much more cleaner to read and understand. The merging of these two data files will fulfills the requirement. I import one of the data sets in line 2 with the seasons variable. Then merge it with the 2022 season data on line 11.



# Analyze Data

## To begin my analysis of my data I create Rank columns for expected and actual touchdowns. This will show me where Quarterbacks rank in actual touchdowns and expected touchdowns. The next part of my analysis is to identify negative and positive regression candidates. To do this I subtract the Expected touchdowns from the Actual touchdowns. A negative number means that they would trend towards scoring fewer touchdowns. A positive number means they would trend towards scoring more touchdowns. This gives me the information I need to make decisions on which Quarterbacks to priortize in drafts and which Quarterbacks to possibly avoid when drafting.

# Interpret Your Data and Graphical Output

## The first graphical output is the yardline_100 graph - This graph shows the probablity of a touchdown from the 99 yard line to the 1 yardline. The graph shows the further you get from the endzone the probablity of a pass touchdown goes down. This makes sense to me and was expected. If I would have got different results, I would have looked into my data to make sure there weren't any errors.

## The second graphical out is showing that if a player is below the blue line they are in line for positive regression meaning potentially more touchdowns and if a player is above the line they are possibly a candidate for fewer touchdowns. This is significant to me because touchdowns are the most important stat when it comes to fantasy football so if you able to identify players who could potentially do better this season and draft them it can give you an advantage. I was also able to make a second graph that is interactive base on player selection so you can select the individual quarterback you are interested in and see where they fall on the chart. I fulfills the visulaization requirement with the three different visualization in Seaborn (line 8) then the matplotlib visualizations (line 19)


## Data Dictionary(fulfills the best practices requirement)

### qb_df

| Field             | Data Type | Description                                                |
| ----------------  | --------- | ---------------------------------------------------------- |
| pass_attempt      | Float     | to throw the football to a reciever                        |
| pass_touchdown    | Float     | A touchdown scored by throwing the football                |
| yardline_100      | Float     | This accounts for each yardline on a football field        |
| two_point_attempt | Float     | The extra point play after a touchdown that counts as two  |

### qb_prob

| Field                           | Data Type | Description                                                                   |
| ------------------------------  | --------- | ----------------------------------------------------------------------------- |
| yardline_100                    | Float     | This accounts for each yardline on a football field                           |
| pass_touchdown                  | Float     | A touchdown scored by throwing the football                                   |
| probability_of_pass_touchdown   | Float     | The percentage chance of a passing touchdown from each individual yardline    |

### exp_df

| Field                      | Data Type | Description                                                    |
| -------------------------  | --------- | -------------------------------------------------------------- |
| Player                     | String    | The Quarterback in the dataset.                                |
| ID                         | String    | Indentification number in dataset.                             |
| Team                       | String    | The NFL team the Quarterback plays for                         |
| Expected Touchdowns        | Float     | The expected number of touchdowns based on probablility model  |
| Actual Tochdowns           | Float     | The actual statistical number of touchdowns thrown             |
| Expected Tochdowns Rank    | Float     | The rank of expected touchdowns thrown                         |
| Actual Tochdowns Rank      | Float     | The rank of actual touchdowns thrown                           |
| Regression Candidate       | Float     | Positive or negative chance at touchdowns thrown               |
| Regression Rank Candidate  | Float     | Rank of positive or negative chance at touchdowns thrown       |


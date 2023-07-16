# Fantasy Football Project Part Two

## Installing this requirements text will install all packages needed to run my program
## pip install -r requirements.txt. Python Version 3.9.10 - It is important to use this version of Python because NFL Data Py does not work with newer versions of Python. When running my program in the Jupyter Notebook, I would run each line one at a time because it is much faster this way instead of hitting run all.

# Read in Data

## I read in my data from the NFL Data Py module. This module gave me play by play data from NFL seasons and allowed me to do the analysis I wanted to do. I created two datasets from NFL Data Py. One was the past seasons, this data allowed me to create a model for probability of a touchdown base on passed season. The second dataset was the 2022 NFL season. I then merged the two datasets to allow me to analyze the Expected and Actual Touchdowns from NFL Quarterbacks in the 2022 season.


# Manipulate and Clean Data

## I started out using some keywords to find Quarterback related columns in my dataset. Once I found these, I created a Quarterback dataframe with only the revelent columns to NFL Quarterbacks. I sorted by yardline_100 to find the instances of a passing touchdown from each yardline. I did a groupby with pass_touchdown and yardline_100 and got the value counts to create a new qb_prob dataframe. The purpose of this dataframe is to give me the probability of a passing touchdown from each yardline. Once I get this dataframe, I realize that I have the probability of not scoring a passing touchdown but I don't want this so I drop any value that equals zero meaning no passing touchdown. Now, I'm ready to Merge my data with the 2022 NFL Season data. Once, I do this I have a little more clean up to do. I rename several of the columns to make them much more cleaner to read and understand.



# Analyze Data

## 

# Interpret Your Data and Graphical Output

## The first graphical output is the yardline_100 graph - This graph shows the probablity of a touchdown from the 99 yard line to the 1 yardline. The graph shows the further you get from the endzone the probablity of a pass touchdown goes down. This makes sense to me and was expected. If I would have got different results, I would have looked into my data to make sure there weren't any errors.

## The second graphical out is showing that if a player is below the blue line they are in line for positive regression meaning potentially more touchdowns and if a player is above the line they are possibly a candidate for fewer touchdowns. This is significant to me because touchdowns are the most important stat when it comes to fantasy football so if you able to identify players who could potentially do better this season and draft them it can give you an advantage. I was also able to make a second graph that is interactive base on player selection so you can select the individual quarterback you are interested in and see where they fall on the chart.
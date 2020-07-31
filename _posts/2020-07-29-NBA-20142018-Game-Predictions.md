---
layout: post
title: Predicting the Winner of Every NBA Game From 2014-2018
subtitle: How Predicitive Models Increase Our Chances of Winning Bets
cover-img: /assets/img/refs.png
---


## Las Vegas vs the World

  In the world of Sports Gambling there is a phrase that bettors commonly use: “Vegas always knows”. This phrase developed from Las Vegas Sportsbooks predicting the winner of sport events at a rate that is unfathomable. In 2018, Las Vegas Sportsbooks profitted 300 million dollars off public bets. How do Oddsmakers seemingly always predict the outcomes of games. Luck? No. They do it by using data, statistics, and predictive modeling. Below I will sample for you just how Las Vegas does this; I will demonstrate it with a dataset from Kaggle.com that shows if the Home Team Won or Lost during all NBA games from 2014-2018.

## The Data
Below is a graphic of what the dataset looks like. As you can see, it has many different features such as "Steals, Turnovers, Rebounds, Shot Attempts, ect.." Due to the mass amount of features in this data set, some were forced to be cut from the image. I did remove a few features as well. "Total points, opponent total points, field goal %, ect.." were removed to avoid creating a predictive model that already knows the outcome of the game, we don't that. We want to predict the winner without already knowing. For comparission later on, we have baseline accuracy of 50.00%, which just means if you were to guess, you would be able to guess accurate 50.00% of the time.

![data](https://raw.githubusercontent.com/Lucas-Petrus/Lucas-Petrus.github.io/master/_posts/NBAdfHead.jpg)


## How Oddsmakers Make Predictive Models Better
  Oddsmakers are presented the same data that anyone watching basketball can obtain, in fact literally anyone in the world can go grab this data set I used and try to make a predictive model. Oddsmakers are smart though, they know you have access to this information, so they engineer new features into their datasets. They take existing data and make new data with it. Let me demonstrate. 
  
  The graphic below shows 2 of the 10 new columns I created: "Assist/Turnover Ratio" and "Game Changers". From watching and playing basketball I already knew that 'Assists' are a sign your team is playing fluidly together, and turnovers mean you are not playing well together. I thought making a ratio for the Good:Bad would give my model additional predictive power. The Game Changers column is a combination of 'Blocked Shots' and 'Steals'. I call these 'Game Changers' because in an arena when a team playing defense blocks a shot or steals a pass, it changes the energy in the crowd. A crowd of 30,000 people screaming that your shot was blocked is very intimidating, hence the name 'Game Changer'. Much like Las Vegas, I used my previous knowledge of basketball in conjuction with extensive data to better my models predicitve nature. 
  
![data](https://raw.githubusercontent.com/Lucas-Petrus/Lucas-Petrus.github.io/master/_posts/AssistGameChangers.jpg)

## Two Models, Two Outcomes
  Now to the good stuff. I took the majority of the original data and my newly engineered features, and placed them into two different types of Logistic Regression models. I choose two differnt types to see if one method was better than the other for this case. For these models, I split my data into a training, validation, and testing set. I trained my model on games before 2016, validation then predicted games between 2016-2017, and testing predicted the 2018 season. One model achieved a validation score of 85.7%, while the other achieved a validation score of 86.1%. Very happy with both, as both these scores predicted the winner of games at a very high rate. Seeing as most professional sports gamblers end a season with around 60% of bets guessed correctly, I will gladly take these score. In the next section, lets look at what features were most predictive.
  
![data](https://raw.githubusercontent.com/Lucas-Petrus/Lucas-Petrus.github.io/master/_posts/TestingAcc.jpeg)

## What Features Were Most Predictive?
  The image below shows a bar graph of the most predictive features in my model. Important to note that the top 4 features were not provided for use in the original data. 'Defensive Rebounds', 'Opponents Defensive Rebounds', 'AssistTurnover Ratio', and 'Opponent AssistTurnover Ratio' were all enginereed by me. This is why having previous knowledge about what you are trying to predict is important. I knew that defensive rebounds were important to add because defensive rebounds prevent the other team a second chance at scoring a basket. I knew assist and turnovers are very telling of how a team is executing their offense. Are they passing the ball aimlessly or with purpose, that ratio helps to determine that factor. Anyone (with time) can make a predictive model, but the more you understand about a subject before diving into the data, the more predictive you can make your model.
  
![](https://raw.githubusercontent.com/Lucas-Petrus/Lucas-Petrus.github.io/master/_posts/GraphTry.jpg)
  
## Now Lets Explore
  Now that we know which features in our model were most predicitive, lets dive a little deeper. First, lets compare 'OpponentsDefRebounds' and 'OpponentsAssistTurnoverRatio' since these were two of our most predicitive features. Notice how when 'OpponentsAssitTurnoverRatio' goes all the way up, and 'OpponentsDefRebounds' go all the way up, the probablity of the home team winning that game is 11.00%. This makes perfect sense because these two statistics show how well a team is controlling the basketball. Controlling the ball and not giving up extra shots will help you win game.
![](https://raw.githubusercontent.com/Lucas-Petrus/Lucas-Petrus.github.io/master/_posts/PDP1.jpeg)

  Let's look at some features from the Home Teams, and see how these predicted: 'Total Fouls' and 'Turnovers'. As you can see, when 'Total Fouls' and 'Turnovers' trend all the way up, the Home Team's winning probability becomes 37.9%. This is shocking to me actually. I was expecting these features to have a much greater impact on the probability of winning. Turnovers means you aren't playing smart basketball, you keep giving the opponent the ball, you have less chances to score. This forces coaches to make shifts in the lineups to see if something else might work. Could this open the discussion that coaching is a lot more important than the general public might think? It should, lets see what happens with fouls. I see fouls as incredibly detrimental to a team, but I was expecting a far greater impact since fouls force good players to sit, give the other team more opportunity to score. Again this alludes to coaching adjustments. I was surprised by these results, but am happy to see this. I now know coaching must help offset problems teams face. You would think a group of 30 year old professional athletes would be good enough without the coach, but apparently that is not the case.
![](https://raw.githubusercontent.com/Lucas-Petrus/Lucas-Petrus.github.io/master/_posts/TotalFouls.jpg)


## Final Thoughts
  Las Vegas Sportsbook aren't money machines because they are better at watching NBA games then us, but they are smarter in their approaches. They see how powerful data, statistics, and numbers are. The human mind is influenced by emotion, and gambling is an emotional rollarcoaster. If you can remove the emotional influence, and use math and computers to make predictions instead, don't be shocked when you start hitting a lot more of your bets. 

---
layout: post
title: Predicting the Winner of Every NBA Game From 2014-2018
subtitle: How Predicitive Models Increase Our Chances of Winning Bets
cover-img: /assets/img/refs.png
---


## Las Vegas vs the World

  In the world of Sports Gambling there is a phrase that bettors commonly use: “Vegas always knows”. This phrase developed from Las Vegas Sportsbook Oddsmakers frequently guessing the winner of games, as well as how much the winning team wins by to prefection. In 2018, Las Vegas Sportsbooks profitted 300 million dollars off public bets. 300 million dollars from being able to more accurately guess the outcome of sporting events. Imagine a life where you could just watch sports all day and make that amount of money. How do Oddsmakers seemingly always predict the outcomes of games. Luck? No. Rigged Games? No (but maybe sometimes, see previous blog post). They do it by using data, statistics, and predictive modeling. Below I will sample for you just how Las Vegas does this; I will demonstrate it with a dataset from Kaggle.com that has the winner of every NBA game from 2014-2018.

## The Data
Below is a graphic of what the dataset looks like. As you can see, it has many different features such as "Steals, Turnovers, Rebounds, Shot Attempts, ect..". I removed a few features such as "total points, opponent total points, field goal %, ect.." as these are all features that would already be able to tell our model who won the game. We dont want, we want to predict the winner without already knowing. For comparission later on, we have baseline accuracy of 50.00%, which just means if you were to guess, you would be able to guess accurate 50.00% of the time.

![](NBAdfHead.jpg)


## How Oddsmakers Make Predictive Models Better
  Oddsmakers are presented the same data that anyone watching basketball can obtain, in fact literally anyone in the world can go grab this data set I used and try to make a predictive model. Oddsmakers are smart though, they know you have access to this information, so they engineer new features into their datasets. They take existing data and make new data with it. Let me demonstrate, the graphic below now has new columns I created, two of which are called "Assist/Turnover Ratio" and "Game Changers". From watching and playing basketball I already knew that Assists are a sign your team is playing fluidly together, and turnovers mean you are not playing well together. I thought making a ratio for the Good:Bad would give my model additional predictive power, power it did not have before. The Game Changers column is a combination of Blocked Shots and Steals. I call these game changers because in an arena, when a team playing defense blocks a shot or steals a pass it gives life and noise from the crowd. A noisey crowd makes for a difficult playing envirnoment, hence Game Changer. I used my knowledge of basketball in conjuction with data to make a more accurate prediction on the outcome of the game. Additional features were added, but for the sake of your time, I wanted to limit discuss to these two.
 
![](AssistGameChangers.jpg)

## Two Models, Two Outcomes
  Now to the good stuff. I took the majority of the original data and my newly engineered features, and placed them into two different types of Logistic Regression models. I choose two differnt types to see if one method was better than the other for this case. For these models, I split my data into a training, validation, and testing set. I trained my model on games before 2016, validation then predicted games between 2016-2017, and testing predicted the 2018 season. One model achieved a validation score of 85.7%, while the other achieved a validation score of 86.1%. Very happy with both, as both these scores predicted the winner of games at a very high rate. Seeing as most professional sports gamblers end a season with around 60% of bets guessed correctly, I will gladly take these score. 
  

## What Did and Didn't Surprised Me?
  After I ran my model and got my validation accuracy of 86.1%, I was curious to see which features were most helpful in making predictions. The bar graph below confirmed one of my initial thoughts about the feature 'Assist/Turnover Ratio'. When you move the ball well on offense, and limit the amount of times you accidently lose the ball to the other team, your chances of winning go up. This is also true for the most predictive feature "rebounds", anytime you are on defense and a team shoots and misses, collecting a rebound prevents them from scoring again. The more rebounds you have says a few things "the other team is missing shots often, and they are not getting a second chance opportunity to score". Lastly, the Game Changers feature was a good choice, blocks and steals cause issues. Whether those issues are results of mental barriers that I believe arise from blocks and steals, I can't officially say, but its a good to see my thought process was correct.
  What did surpise me was that the East and West opponents columns did nothing to my models predicitive power. I was a very very firm believer that playing Western Conference opponents would impact my model greatly, but now that I see the outcome, I'm glad it didnt and here is why. As gamblers we tend to get to caught up in what we visibily see happening. We visibilly see Western Conference opponents scoring so many points its unbelievable at times, and now I realize that in a sense it is unbelievable. The Western Conference might have teams scoring many points, but the tradeoff is defense. They give up a lot of points to becasue they play lazy defense. It is awesome to see the model picking up on that and helping me stray away from "the eye test"
![](GraphTry.jpg)
  
#
  


## Final Thoughts
It should be clear after reading this data that Referees have a much larger impact on the game than most may believe. The simply action of calling an extra foul on an oppossing team can be a deciding factor in the outcome of the game. With nationwide legalized gambling getting ready to launch these upcoming seasons, its more important that ever to protect the integrity of officiating in the NBA, and make light of situations we as viewers deem to be 'strange' or 'off'

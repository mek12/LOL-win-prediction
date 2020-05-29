# LOL-win-prediction

## Data Set
https://www.kaggle.com/bobbyscience/league-of-legends-diamond-ranked-games-10-min

## Introduction
  League of Legends is a brisk, competitive, online game combining the excitement of strategy games with elements of role-playing games. Two teams of champions, unique in design and gameplay, compete head-to-head in various battlefields and game modes. League of Legends is a game that players of all skill levels can play for a very long time without getting bored, with its constantly varying champions, frequently updated content and live tournament environment. League of Legends is a struggle of 2 teams of 5 each to demolish each other's center on a map of 3 corridors.
  
  
   This dataset contains the first 10min. stats of approx. 10k ranked games (SOLO QUEUE) from a high ELO (DIAMOND I to MASTER). Players have roughly the same level. There are 19 features per team (38 in total) collected after 10min in-game. This includes kills, deaths, gold, experience, level… It's up to you to do some feature engineering to get more insights. The column blueWins is the target value (the value we are trying to predict). A value of 1 means the blue team has won.

## Preprocessing
  After the examinations, it was observed that some features did not affect the winning condition.
  
- **drop_cols** = ["gameId","blueWardsPlaced","blueWardsDestroyed", "blueEliteMonsters", "blueTotalExperience", "blueTotalJungleMinionsKilled", "blueCSPerMin", "blueGoldPerMin", "redWardsPlaced", "redWardsDestroyed", "redEliteMonsters", "redTotalExperience", "redTotalJungleMinionsKilled","redCSPerMin","redGoldPerMin"]

- **lol_df_clean**=lol_df.drop(["blueTotalMinionsKilled","blueFirstBlood", "blueAssists","blueDeaths","blueHeralds","blueTotalMinionsKilled","blueDeaths","blueTowersDestroyed","redDeaths", "redAssists", "redHeralds","redTotalMinionsKilled","redFirstBlood","redTowersDestroyed"],axis=1)

## Result
It was used 
- Naive Bayes, 
- Logistic Regression
- KNN

The best result was from Naive Bayes.

- Naive Bayes           **Accuracy**: 72.82 %
- Logistic Regression   **Accuracy**: 72.26 %
- KNN                   **Accuracy**: 71.30 %

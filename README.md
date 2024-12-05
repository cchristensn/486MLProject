This is the repository for my stat 486 ML project
The aim is to predict an 'underground' boardgame's rating


#### BoardgamesEDA.ipynb
This file reads in from `boardgames_ranks.csv` and uses the BGG XML API to create `testingdata.csv` and `trainingdata.csv`. Loops are modular, but you need to replace objects 'by hand' to get the dataframes you want/need.

#### BoardgamesCleaning.ipynb
Transforms the *categories* and *mechanics* columns found in `trainingdata.csv` and `testingdata.csv` from lists to onehot encoded individual categories and mechanics

(e.g. if a game has the categories *Trains* and *Healthcare* in the form `['Trains','Healthcare']`, it transforms into two columns `Trains` and `Healthcare` with the value of 1. All other categories have the value of 0)

File results in the creation of `cleantesting.csv` and `cleantraining.csv`
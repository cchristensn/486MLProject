This is the repository for my stat 486 ML project
The aim is to predict an 'underground' boardgame's rating


#### BoardgamesEDA.ipynb
This file reads in from `boardgames_ranks.csv` and uses the BGG XML API to create `testingdata.csv` and `trainingdata.csv`. Loops are modular, but you need to replace objects 'by hand' to get the data frames you want/need.

#### BoardgamesCleaning.ipynb
Transforms the *categories* and *mechanics* columns found in `trainingdata.csv` and `testingdata.csv` from lists to one-hot encoded individual categories and mechanics

(e.g. if a game has the categories *Trains* and *Healthcare* in the form `['Trains','Healthcare']`, it transforms into two columns `Trains` and `Healthcare` with the value of 1. All other categories have the value of 0)

Also creates new features extracting numeric values from `descriptions` such as sentence count, description length, unique word count, and special character count.

File results in the creation of `cleantesting.csv` and `cleantraining.csv`

#### BoardgamesSupervised.ipynb
Creates 4 supervised ML model and predicts scores for the games found in `cleantesting.csv`.
Outputs the predictions in `SupervisedPredictions.csv`

Also performs a feature importance analysis using SHAP, to add a little more interpretability to my best performing model.

#### Deeplearning.ipynb
Creates an ANN model trained on `cleantraining.csv`. Outputs the predictions in `DeeplearningPredictions.csv`

#### BoardgamesClustering.ipynb
Performs a cluster analysis on both the properly ranked games and the games with unknown ranks. No output files, but determined they types of games I'm dealing with.

Visualized clusters with both the most influential variables (found using SHAP) and using UMAP to reduce the dimensions of the data.

#### stopwords.txt
A text file of stop words used for encoding the text data
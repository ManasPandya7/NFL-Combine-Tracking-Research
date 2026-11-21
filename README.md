# NFL Combine Tracking Research

## About this project

I wanted to see whether movement data from the NFL Combine could help predict how much playing time a player gets in the NFL.

The idea was to compare the usual Combine measurements with additional tracking information, such as speed and acceleration, and check whether that extra data actually improves predictions.

## Dataset

I used the NFL Big Data Bowl 2027 dataset from Kaggle.

https://www.kaggle.com/competitions/nfl-big-data-bowl-2027/data

I focused on players from the 2025 draft class who had 40-yard-dash tracking data available. This gave me 133 players for the analysis.

## What I did

I started by loading the data and checking for missing values. I joined the player information, Combine results, tracking measurements and career outcomes using player IDs.

I then created a few tracking features based on speed and acceleration.

To compare the results fairly, I used logistic regression as a baseline and then tested the same model with tracking features added. I also tried a random forest to see whether a different approach performed better.

I used repeated cross-validation to evaluate the models.

## Results

| Model | ROC-AUC |
|---|---|
| Traditional Combine model | 0.803 |
| Traditional + tracking | 0.791 |
| Random forest with tracking | 0.770 |

The traditional model performed slightly better in this experiment. Adding the tracking features did not improve the predictions.

This was interesting because I expected the extra movement information to help. It reminded me that adding more features does not always lead to a better model.

## Limitations

The sample was small, and playing time is affected by coaching decisions, injuries and team opportunities. The data also contains cumulative career outcomes, so the reporting period needs to be considered.

I would like to try more detailed movement features and additional seasons before drawing stronger conclusions.

## How to run

1. Download the NFL Big Data Bowl 2027 dataset from Kaggle.
2. Keep the Kaggle ZIP in the same folder as the notebook.
3. Install the Python packages using `pip install -r requirements.txt`.
4. Open `NFL_Combine_Tracking_Research.ipynb` in Jupyter.
5. Run all the cells to reproduce the analysis.

## Tools

Python, Pandas, NumPy, Matplotlib and Scikit-learn.
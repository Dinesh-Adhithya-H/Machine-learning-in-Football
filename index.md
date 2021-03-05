![render (3)](https://user-images.githubusercontent.com/68704516/110153134-a780b400-7e08-11eb-9629-3488c804ff48.png)
# Welcome !!

We hope you find our work enjoyable and interesting , where our current interest lies on using Machine Learning techniques to model sports event data.
Check out our [project](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football) .

Contributors: [Dinesh Adhithya](https://github.com/Dinesh-Adhithya-H) and [Sachin Mishra](https://github.com/nihcaSInParis)

If you wish to reach out to us : [Dinesh Adhithya](mailto:hdinesh18@iiserb.ac.in) and [Sachin Mishra](mailto:sachin18@iiserb.ac.in)

## 1. Modelling pass difficulty/hardness in football matches.


### Data Extraction and parsing

We use Statsbomb event data available at the [Statsbomb github repository](https://github.com/statsbomb/open-data) and collect the passes from each match to make our dataset.
We have 861714 datapoints in our dataset, we need to make sure our training dataset has equal no. of completed and incomplete passes. So we select 173101 completed and Incomplete passes to form our training dataset.


### Data Exploration

[pass outcome distribution of our dataset](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/pass_distribution.png)

[pass dataset](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/passes_exploration.png)


### Model selection

We look to model each pass using a set of features that describe a pass , namely :

1. pass length
2. pass angle
3. pass start coordinates
4. pass end coordinates 
5. pass duration

We use machine learning models such as LinearRegression , Graphical Boosting models , Deep Neural Network models , etc. to predict the difficulty of a pass being completed.
Each pass in training dataset is assigned 1 for a completed pass and 0 for an incomplete pass. Then such model is used on match event data to find the difficulty of passes completed during a match. A new metric called expected pass is being made by us , inspired from Xg models developed before. This metric quantifies the pass difficult which assigns each pass a value between 0 and 1 , 1 indicates a tough pass and 0 indicates an easy pass.

Deep Learning model performs at an accuracy of ~80% and is the best performing model. This model is used for application on match data.


### Model Application

The model was used on a few matches contested by FC Barcelona , The following pass hardness distributions were obtained :
- X-axis : 0 to 10, pass hardness increases from 0 to 10.
- Y-axis : No. of passes of that particular difficulty.

[FCB VS ALMERIA](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20almeria.png)
[FCB VS BILBAO](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20bilbao.png)
[FCB VS ESPANYOL](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20espanyol.png)
[FCB VS GRANADA](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20granada.png)
[FCB VS OSASUNA](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20osasuna.png)
[FCB VS REAL BETIS](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20real%20betis.png)
[FCB VS VILLAREAL](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20villareal.png)


[A plot of pass Hardness of passes involved during a possession from the match between FCB VS Granada](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/possession.png)

### Observations

The pass difficulty histogram falls exponentially with increasing pass hardness. Passes being the most common event during football matches these plots give us an idea how risk is optimised during football matches. Passes also goes on to be the most commom type of interaction among players. Our work ponders more deeply on how a closed group of humans interact with each other and the possible application of such ideas is also being explored upon.



## 2. Modelling Expected Goals of shots taken during football matches using Machine Learning.


### Data Extraction and parsing
We make use of Statsbomb's open data and use ~ 13 k shots to model the probablity of a shot taken ending up as a goal.

### Data Exploration

[shots dataset](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/shots_exploration_1.png)
[shot locations](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/shots_histogram.png)
[goal locations](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/goals_histogram.png)

### Model selection

The following features describing the shot were used :

1. body part from which shot was taken from.
2. technique used in the shot.
3. no. of opponents in the triangle joning the 2 end points of goal post and shot position.
4. no. of teammates	in the triangle joning the 2 end points of goal post and shot position.
5. location of the shot
6. angle the shot location makes with the 2 goal posts.
7. distance from goal

The best performing ML model was deep neural networks which performed at an accuracy of ~ 87 % on testing dataset.

[shot distribution plot obtained from our model](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/shot_distribution.png)


### Model Application

The model was applied on the testing dataset and following Xg histogram for no. of shots vs Xg was obtained and compared to Statsbomb's Xg model.

[Model prediction](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/82e0d69445428cbb65ff2e4be910c12b4c6ae878/shots_histogram_model_vs_statsbomb.png)
[Statsbomb's prediction](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/shots_histogram_model_vs_statsbomb_1.png)

### Observations

The histogram obtained by our model was in the shape of a bell curve , with maximum of the curve at an Xg of ~0.1 , whereas the statsbomb model's curve is an exponentially falling  curve whose maximum is at an Xg of 0.0. Intution suggests the curve obtained by our model makes more sense but unless a larger dataset is used for the same work we cant draw conclusions.

## 3. Dribble Modelling 

### Data Extraction and parsing
We collected ~36k dribble event data from the Statsbomb open data.

### Data Exploration

[Dribble histogram](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/dribble_hist.png)
[Dribble attempted locations](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/dribbles.png)
[Dribble successful locations](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/success_dribbles.png)
[Proportion of successful dribbles](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/prop_success_dribbles.png)

### Model selection and Application

The model predicts the probability of a successful dribble , called Xd and outputs to be predicted are set as 1 for complete dribble and 0 for incomplete dribble.
The best performing model had an accuracy of ~60% on the testing datasets.

Our model's [performance](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football/blob/main/Xd.png) on testing dataset.

### Observations

Dribbles have a minimum Xd of 0.113 and maximum Xd of 0.83.  

## Weightage to each event.

1. Avg. success rate of a dribble : 0.618
2. Avg. success rate of a pass : 0.797
3. Avg. success rate of a shot : 0.119

These happen to most often events in possession leading to a shot

## A Improved Xg Chain Model

[Statbomb's Xg Chain Model](https://statsbomb.com/2018/08/introducing-xgchain-and-xgbuildup/)

The proposed model calculates ![render (3)](https://user-images.githubusercontent.com/68704516/110153181-b9faed80-7e08-11eb-89c1-dbaed3b7158c.png)



















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

pass outcome distribution of our dataset:
![pass_distribution](https://user-images.githubusercontent.com/68704516/110153711-6a68f180-7e09-11eb-849f-c64d9981901b.png)


pass dataset:
![passes_exploration](https://user-images.githubusercontent.com/68704516/110154013-c3d12080-7e09-11eb-9f91-d071fe57fe50.png)



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

FCB VS ALMERIA:
![fcb vs almeria](https://user-images.githubusercontent.com/68704516/110153695-676e0100-7e09-11eb-8e0c-76d819f76d0b.png)

FCB VS BILBAO:
![fcb vs bilbao](https://user-images.githubusercontent.com/68704516/110153697-68069780-7e09-11eb-917d-b1ce34c7dbcf.png)

FCB VS ESPANYOL:
![fcb vs espanyol](https://user-images.githubusercontent.com/68704516/110153701-68069780-7e09-11eb-983d-4d7b919c9dea.png)

FCB VS Getafe:
![fcb vs getafe](https://user-images.githubusercontent.com/68704516/110153703-689f2e00-7e09-11eb-9d51-91973fd026c9.png)

FCB VS GRANADA:
![fcb vs granada](https://user-images.githubusercontent.com/68704516/110153704-689f2e00-7e09-11eb-871e-4eed361e343b.png)

FCB VS OSASUNA:
![fcb vs osasuna](https://user-images.githubusercontent.com/68704516/110153706-6937c480-7e09-11eb-8715-1a1774687d99.png)

FCB VS REAL BETIS:
![fcb vs real betis](https://user-images.githubusercontent.com/68704516/110153708-69d05b00-7e09-11eb-9ba3-526950ccdcdf.png)

FCB VS VILLAREAL:
![fcb vs villareal](https://user-images.githubusercontent.com/68704516/110153709-69d05b00-7e09-11eb-999c-dcc458f3011e.png)



A plot of pass Hardness of passes involved during a possession from the match between FCB VS Granada:

![possession](https://user-images.githubusercontent.com/68704516/110153715-6b018800-7e09-11eb-944e-91557574bd56.png)


### Observations

The pass difficulty histogram falls exponentially with increasing pass hardness. Passes being the most common event during football matches these plots give us an idea how risk is optimised during football matches. Passes also goes on to be the most commom type of interaction among players. Our work ponders more deeply on how a closed group of humans interact with each other and the possible application of such ideas is also being explored upon.



## 2. Modelling Expected Goals of shots taken during football matches using Machine Learning.


### Data Extraction and parsing
We make use of Statsbomb's open data and use ~ 13 k shots to model the probablity of a shot taken ending up as a goal.

### Data Exploration

shots dataset:
![shots_exploration_1](https://user-images.githubusercontent.com/68704516/110153725-6d63e200-7e09-11eb-84d6-f66c85e294cf.png)

shot locations:
![shots_histogram](https://user-images.githubusercontent.com/68704516/110153726-6e950f00-7e09-11eb-87e2-6631442608f1.png)

goal locations:
![goals_histogram](https://user-images.githubusercontent.com/68704516/110153710-6a68f180-7e09-11eb-96ef-daa21032271a.png)


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

shot distribution plot obtained from our model:
![shot_distribution](https://user-images.githubusercontent.com/68704516/110153721-6ccb4b80-7e09-11eb-9124-f8901fc39b72.png)


### Model Application

The model was applied on the testing dataset and following Xg histogram for no. of shots vs Xg was obtained and compared to Statsbomb's Xg model.

Model prediction:
![shots_histogram_model_vs_statsbomb](https://user-images.githubusercontent.com/68704516/110153729-6e950f00-7e09-11eb-90c2-0323059ff5cf.png)

Statsbomb's prediction:
![shots_histogram_model_vs_statsbomb_1](https://user-images.githubusercontent.com/68704516/110153731-6f2da580-7e09-11eb-90b3-afd9cbe66e4d.png)


### Observations

The histogram obtained by our model was in the shape of a bell curve , with maximum of the curve at an Xg of ~0.1 , whereas the statsbomb model's curve is an exponentially falling  curve whose maximum is at an Xg of 0.0. Intution suggests the curve obtained by our model makes more sense but unless a larger dataset is used for the same work we cant draw conclusions.


## 3. Dribble Modelling 


### Data Extraction and parsing

We collected ~36k dribble event data from the Statsbomb open data.

### Data Exploration

Dribble histogram:
![dribble_hist](https://user-images.githubusercontent.com/68704516/110153687-663cd400-7e09-11eb-985c-f16ab261ab32.png)

Dribble attempted locations:
![dribbles](https://user-images.githubusercontent.com/68704516/110153690-676e0100-7e09-11eb-8823-51b7c317c36a.png)

Dribble successful locations:
![success_dribbles](https://user-images.githubusercontent.com/68704516/110153732-6f2da580-7e09-11eb-9de3-e7e9b42c39cc.png)

Proportion of successful dribbles:
![prop_success_dribbles](https://user-images.githubusercontent.com/68704516/110153720-6c32b500-7e09-11eb-960b-e4d2f4a9178a.png)


### Model selection and Application

The model predicts the probability of a successful dribble , called Xd and outputs to be predicted are set as 1 for complete dribble and 0 for incomplete dribble.
The best performing model had an accuracy of ~60% on the testing datasets.

Our model's performance on testing dataset:
![Xd](https://user-images.githubusercontent.com/68704516/110153733-6fc63c00-7e09-11eb-8223-1300741b4d94.png)


### Observations

Dribbles have a minimum Xd of 0.113 and maximum Xd of 0.83.  

## Weightage to each event.

1. Avg. success rate of a dribble : 0.618
2. Avg. success rate of a pass : 0.797
3. Avg. success rate of a shot : 0.119

These happen to most often events in possession leading to a shot

## A Improved Xg Chain Model

[Statbomb's Xg Chain Model](https://statsbomb.com/2018/08/introducing-xgchain-and-xgbuildup/) has a primitive definition of Xg build up and our model gives weightage to difficulty of tasks performed leading to a shot.

The proposed model calculates:
![render (3)](https://user-images.githubusercontent.com/68704516/110153181-b9faed80-7e08-11eb-89c1-dbaed3b7158c.png)







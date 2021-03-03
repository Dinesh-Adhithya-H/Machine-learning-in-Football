# Welcome !!

We hope you find our work enjoyable and interesting , where our current interest lies on  using  Machine Learning techniques to model sports data.
Check out our project [GitHub Account](https://github.com/Dinesh-Adhithya-H/Machine-learning-in-Football) .

Contributors: Dinesh Adhithya and Sachin Mishra

## Modelling pass difficulty in football matches using Machine Learning.


### Data Extraction and parsing

We use Statsbomb event data available at the [github repository](https://github.com/statsbomb/open-data) and collect the passes from each match to make our dataset.
We have 861714 datapoints in our dataset ,  we need to make sure our training dataset has equal no. of completed and incomplete passes. So we select 173101 completed and Incomplete passes to form our training dataset.


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

![FCB VS ALMERIA](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20almeria.png)
![FCB VS BILBAO](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20bilbao.png)
![FCB VS ESPANYOL](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20espanyol.png)
[FCB VS GRANADA](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20granada.png)
[FCB VS OSASUNA](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20osasuna.png)
[FCB VS REAL BETIS](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20real%20betis.png)
[FCB VS VILLAREAL](https://github.com/Dinesh-Adhithya-H/sports-analytics/blob/master/fcb%20vs%20villareal.png)
![cat]("https://upload.wikimedia.org/wikipedia/commons/e/e9/Felis_silvestris_silvestris_small_gradual_decrease_of_quality.png)

### Observations

The pass difficulty histogram falls exponentially with increasing difficulties. Passes being the most common event during football matches this plots give us an idea how risk is
optimised during football matches. Our work ponders more deeply on how a closed group of humans interact with each other and possible application of such ideas is being explored upon.





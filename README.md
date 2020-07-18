# Depression Analysis Twitter

### Overview
In this project, a LSTM with Convolutional Neural Network is built using Keras to determine whether social platform users are depressive based on their Twitter posts. The accuracy of the model is evaluated and compared to a binary classification baseline model using logistic regression. It is discovered that the model has a 99.26% accuracy after 5 epochs, while the base line model has a much lower accuracy of 84.283%.

### Datasets
There are two kinds of tweets that are needed for this project: random tweets that do not indicate depression and tweets that show the user may have depression. The random tweets dataset can be found from the Kaggle dataset [twitter_sentiment](https://www.kaggle.com/ywang311/twitter-sentiment/data). It is harder to get tweets that indicate depression as there is no public dataset of depressive tweets, so in this project tweets indicating depression are retrieved using the Twitter scraping tool [TWINT](https://github.com/haccer/twint) using the keyword `depression` by scraping all tweets in an one day span. The scrapped tweets may contain tweets that do not indicate the user having depression, such as tweets linking to articles about depression. As a result, the scrapped tweets need to be manually checked for better testing results. A csv file of scrapped tweets is provided, however the following code can be used to obtain depressive tweets for this project, keep in mind that the date in the code should be changed and the generated .csv file should be manually checked and moved to the project directory:
```sh
python3 twint.py -s depression --since 2018-05-15 -o depressive_tweets_processed.csv --csv
```

#### Test Data Split
Collected tweets are split into training, testing, and validation sets with a ratio of 60%:20%:20%.

|               | Depressive Tweets           | Normal Tweets  |
| ------------- | --------------------------- | -------------- |
| Training      | 1384                        | 7146           |
| Validation    | 462                         | 2382           |
| Testing       | 462                         | 2383           |
| Total         | 2308                        | 11911          |

### Required Libraries
* ftfy - fixes Unicode that's broken in various ways
* gensim - enables storing and querying word vectors (Embedding File : https://www.kaggle.com/sandreds/googlenewsvectorsnegative300)
* keras - a high-level neural networks API running on top of TensorFlow
* matplotlib - a Python 2D plotting library which produces publication quality figures
* nltk - Natural Language Toolkit
* numpy - the fundamental package for scientific computing with Python
* pandas - provides easy-to-use data structures and data analysis tools for Python
* sklearn - a software machine learning library
* tensorflow - an open source machine learning framework for everyone

### How to Run
To run the `Analysis.ipynb` iPython notebook that contains all the code, please run the following line in the project directory:
```sh
$ jupyter notebook
```
### Demo Videos

* Part 1 : https://youtu.be/t5JwGhtwFU4
* Part 2 : https://youtu.be/l_karl3EG_Q

### Authors

* **Usama Naveed** -https://github.com/usamanaveed900)

See also the list of [Projects] (https://github.com/usamanaveed900?tab=repositories) i have woked on.



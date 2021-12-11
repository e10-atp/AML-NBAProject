# AML-NBAProject

Supervised machine learning on NBA dataset
Yimeng Wang(yw2392)
Fanruo Gu(fg285)
Ethan Chang (ec687)


Motivation:
The Naismith Memorial Basketball Hall of Fame is an American history museum and
hall of fame. It is one of the highest honors an NBA player could receive. Since the
building opened in 1968, only 177 basketball players have been admitted to the hall of
fame. Our project aims to predict whether an NBA player will be admitted to the hall of
fame based on the players’ career statistics. The data was downloaded from NBA.com.
We plan to use statistics that are commonly accepted to be indicative of a player’s skill
as modelling features (points per game, rebounds, assist percentage, etc.). If our model
were accurate enough, we could use the model to predict whether an active player can
be admitted to the Hall of Fame once he is retired. We could also find out which
statistics weigh the most when evaluating the qualification of the Hall of Fame.
Method: In our case, the Hall of Fame status is a binary classification vector, so we are
planning to apply several classification models to the data. Models include but are not
limited to logistic regression, Naive Bayes and Gaussian Mixture Model. Since there are
many attributes we could use, we are also considering applying PCA to reduce the
number of features. To test the data, we will use cross-validation.


Experiment: We manually recorded a data set from NBA.com of top players sorted by
most points per game leaders in the regular season. There are 1306 players in our
initial data set, however due to the hall of fame not accepting active players the target
vector for active players cannot be considered to be either true or false. Therefore we
excluded all active players from our data, which left us a feature vector with dimension
1,171. Each x_i has 10 attributes, making the feature vector size 1171 x 10. We cleaned
the data by filling in blank cells with the attribute’s median. We split the data into
training, validation, and test sets then created a preliminary logistic regression model
using the sklearn library.
We visualized the results in a confusion matrix using the seaborn library; preliminary
results look good, but we can still seek to improve our model before applying it. The
numeric result is as follows:
Accuracy: 0.9373219373219374
Precision: 0.8333333333333334
Recall: 0.5952380952380952
The accuracy seems fine but the recall is not that good. This means that the logistic
model is better at predicting non Hall of Famers. If a player is in the Hall of Fame,
there’s around 40% chance the player won’t be predicted correctly. The difference
between accuracy and recall is so big, and this is probably because only very few
players are in the Hall of Fame.


Future work:
With all the work we’ve done so far, our next step is to attempt more models such as
GMM and Native Bayes to determine which one has the highest efficiency. We will also
try to record more data to make our dataset less biased towards point totals by rounding
it out with players that have the highest assists, rebounds, steals, and blocks.

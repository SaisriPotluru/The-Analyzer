
# The Analyzer 
   This hotel chain is well-known for its variety of foods. Experts have claimed that tweaking the menu can improve success by 15%.By this project we could be able to predict the cuisine type based on the ingredients provided and also the nearest Ids of the cuisines.
   
# Author   
 Saisri M Potluru.You can contact me at saisri.m.potluru-1@ou.edu .

# Description
  The data is in a dictonary format which consist of ID , cuisine and the ingredients.
    The format of the data is :
 ~~~

{
  "id": 10276,
  "cuisine": "mexican",
  "ingredients": [
    "chili powder",
    "crushed red pepper flakes",
    "garlic powder",
    "sea salt",
    "ground cumin",
    "onion powder",
    "dried oregano",
    "ground black pepper",
    "paprika"
  ]
}

~~~
The whole data for this project is obtained from https://www.dropbox.com/s/f0tduqyvgfuin3l/yummly.json

The steps involved in the process are as follows:

## 1.Converting the dictonary data to a dataframe
   The data from the file " yummly.json" is loaded and are converted as a dataframe with columns ID,cuisine , ingredients.The ingredients column currently is in the form of a list which has been updated in string format and keept as another column of jointedingredients.
   
## 2.Vectorize the jointed ingredients data
  The whole column is vectorized by using TfidfVectorizer() function
  
## 3.label the cusines
  The cusines are lablled using the LabelEncoder() function.The Cuisines are labelled because they would be in a numerical format but if the numerical format has to have some meaning full values and those values are nothing but diffrent types of cusines.

## 4.Splitting data 
  The data is splitted into training and testing data in the ratio of 80:20 for both cusines and the ingredients,respectively.
  
## 5.Modelling
  For modelling,K-Nearnest Neighbored (KNN), one of the classification method, modelling is used as so that all the ingredients can be classified based on the cusines types and further the prediction can be done.Here,for my model I have considered 'n_neighbors = 12' by comparision of the diffrent n_neighbors's accuracy_score 's .For my model the accuracy score is 0.7415461973601508 which means nothing but the comparision of the model predictions with the test data.
  
## 6.ingredients input - cuisine output
  When a string of ingredients are given then those are vectorized and the model is applied to predict for the provided ingredients and the cusine type is obtained.
  
## 7.Top five nearest cuisine's for the given ingredients 
  For obtaining the cusines,I have used "cosine_similarity" function to calculate the distance of the ingredients to the all set of data by which we could know the best ID's of them.Then those arrays are converted into a dataframe and top five most similar ID's along with their distances are returned.
  
  
# Assumptions
- while giving the input it should be in a string format """a b c """

# External Resources:

https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761
https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html
https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.NearestNeighbors.html
https://stackoverflow.com/questions/30522724/take-multiple-lists-into-dataframe









  









# DataTriumph.<br/>Market Basket Analysis Using Machine Learning.

<b>Team Members:</b> 
<ul>
<li><b>SK SAQLAIN MUSTAQ.</b></li>
<li><b>SUMAIR AHMED SHARIFF.</b></li>
</ul>
<b>The given repository was created as a part of 5th Semester Data Analaytics Project PESU.</b>


Market basket analysis is based upon the identiﬁcation and analysis of purchasing patterns of the customers it helps in scientiﬁc decision support for retail market by mining association rules among items people purchased together. Mining purchasing patterns allows retailers to adjust promotions, store settings and serve consumers better.The process involves an analysis of historic data and based on that analysis to predict the future occurrences or events.In this paper we have proposed multiple model usig k-nn,SVM, MLP to test whether can supervised learning algorithmn can be used to recommend items to users and also implemented a model that would predict whether the item will be reordered or not, using logisticregression algorithm which was also testted witha NN model to check which model performed better and and also a recommending system that will recommend products to customer based on collaborative ﬁltering and using the products which have been re-ordered multiple times that is high demand. 

<br/>
<br/>
<ul><li>HARDWARE REQUIREMENTS:-</li></ul>
<ul><li type=1>python3</li><li type=1>MINIMUM 18gb OF RAM</li></ul>
<br/>
<br/>

<ul>EXECUTE THE FILES IN THE FOLLOWING ORDER:-
  <li type=1>data processing.ipynb</li>
  <li type=1>k-nn.ipynb</li>
 <li type=1>model2.ipynb</li>
 <li type=1>REGRESSION MODEL TO PREDICT WHETHER THE ITEM WILL BE RE-ORDERED OR NOT.ipynb</li>
 <li type=1>** RECOMMENDATION_MODEL.ipynb</li>
 **<p style="size:2px">in-order to replicate the above code a minimum of 18gb ram is required</p>
</ul>

<ul><li>PROPOSED APPROACH:-</li></ul>
As most of the approaches uses Associative rules mining and Apriori based methods thus majority of the time is consumed in generating the rules.

<ul><li type='A'><b>Data processing:-</b></li> 
<p>The transactions that were present in the dataset were in a single column and not in a basket format thus the dataset was processed to get all the items that is ordered by a single user/transaction, and in-order to model the problem with a supervised learning algorithms, each transaction was further processed, thus the code to processed the data is present data-processing.ipynb. </p>
 
<li type='A'><b>Recommending next items using supervised learning approach :-</b></li>
 <ul><li> k-nn:</li></ul>K nearest neighbors is a simple algorithm that stores all available cases and classiﬁes new cases based on a similarity measure (e.g., distance functions). A k-nn model was trained with the above mentioned processed data to predict the next item in the transaction, the model was ﬁt with the processed data distance measure being RMSE. The model was trained multiple times with varying neighbors and on testing against the testing data as shown in the Figure as it can be seen that an optimal number of neighbours being 14 with an accuracy of 27.2% and then the accuracy just drops and becomes saturated. 
<p align="center">
  <img src="neighbours.png" width="500" height="350">
</p>
The main disadvantage of the KNN algorithm is that it is a lazy learner that is it does not learn anything from the training data and simply uses the training data itself for classiﬁcation,  the algorithm must compute the distance and sort all the training data at each prediction, which can be slow if there are a large number of training examples as in the case of instacart dataset . Another disadvantage of this approach is that the algorithm does not learn anything from the training data, which can result in the algorithm not generalizing well and also not being robust to noisy data. 
The code that implements using k-nn algorithm is present in the k-nn.ipynb

<ul><li> SVM:</li></ul> SVM is a supervised machine learning algorithm which can be used for classiﬁcation or regression problems. It uses a technique called the kernel trick to transform the data and then based on these transformations it ﬁnds an optimal boundary between the possible outputs. .SVM is capable of ﬁnding non-linear boundaries among the data-points. The beneﬁt is that it can capture much more complex relationships between data-points without having to perform difﬁcult transformations on the data. A SVM model was also trained with the above mentioned processed data to predict the next item that is likely to be picked up, the model was trained on the training data with default parameters of SVM on testing it against the testing data the model predicted with an accuracy of 23.7%. 
The downside of the above mentioned model is that the training time is much longer as it’s much more computationally intensive.
The corresponding code is available in model2.ipynb
<br/>
<br/>
<ul><li> Multi-Layer Perceptron:</li></ul>A Neural Network model was trained with with 3 layers,layer-1 consisting of 50 neurons layer-2 consisting of 20 neurons and layer-3 consisting of 10 neurons activation function being relu and alpha learning rate being 0.001 with max iteration being 500 and optimizer being adam-optimiser. When the model was tested with the testing dataset an accuracy of 29% was obtained when the models parameter was further changed the models accuracy did not change but remained saturated.
The corresponding code is available in model2.ipynb
<br/>
<p>The below table summariezes the accuracy of the above three model.</p>
<p align='center'>
<img src="https://user-images.githubusercontent.com/31769827/48947929-de44a000-ef58-11e8-8ef7-bf8311db5585.PNG" width="500" height="220">
 </p>
<br/>
The above three models were tested on the Bakery Dataset only, as due to the lack of hardware resources the model could not be applied to the instacart dataset which required enormous amount of memory and time to process the transaction and train the model. The neural network performed better as it is capable of learning complex patterns among the data-points compare to the other methods, but its accuracy can further be improved with further preprocessing of the data-set as mention in the above mentioned Data processing section and proper hardware resources.


<li type='A'><b>Predicting whether an item will be re-ordered or not :-</b></li>
 In order to predict whether the an item will be re-ordered or not the instacart dataset was used which had an additional information whether the product was re-ordered or not.<br/>
 <p align="center">
<img src="https://user-images.githubusercontent.com/31769827/48949290-79d80f80-ef5d-11e8-94f5-8cedd293d31f.PNG" width="500" height="400">
 </p>
 <br/>
 The instacart dataset was spread across multiple ﬁles but only products,aisle,department datasets were used and merged to get the information about which department and aisle the product belongs to. Once the dataset was merged the product name,department name,aisle name were drop only the id’s were kept. The resulting dataset was split into training data and testing data, the size of the training data was 969231 and the size of the testing data was 415386. A Logistic regression model was trained to predict whether the current product will be re-ordered or not On testing on the testing dataset an accuracy of 60% was obtained and the f1-score on the original dataset was around 75%. The above proposed problem statement was also model using a neural network with a single layer consisting of 10 neurons and the accuracy that was obtained was around 62% and with further increase in the levels or neurons per level results in the same accuracy. Thus the above proposed model could be used to predict whether the given product will be re-ordered or not and basked on the information reﬁle of the stocks/items can be performed
 The corresponding code is present in REGRESSION MODEL TO PREDICT WHETHER THE ITEM WILL BE RE-ORDERED OR NOT.ipynb
 <br/>
 
 <li type='A'><b>Recommendation System:-</b></li>
 Collaberative ﬁltering is a technique of prediction based on the collected information from many users. The idea behind collaborative ﬁltering is that if a person-A has the same opinion as person-B than A is more likely to have B’s opinion on different items. 
 <br/>
 As the instacart dataset had information about the transaction about various users on which collaborative ﬁltering could be applied to recommend products to user but it also had the information about a user whether he/she will re-order the product, As the dataset had information of a product being to be re-ordered. That is if a product is likely to be reordered this in turn indicates that, that the product is likely to be picked up by multiple users thus this information along with collaborative ﬁltering is used to recommend products to the users. 
 <br/>
 <ul><li>  Data processing:</li></ul> As the datasets were split-ed among multiple smaller datasets, the datasets were merged to get the information such as product name, the department that it belongs to and the aisle information. As the datasets had informations about a product in a transaction being re-ordered by as user, thus we considered only those rows in which the items have been re-ordered. Considering only those rows in-which the item have been re-ordered more than ones this is because if an item is re-ordered more than once it is more likely to be picked by
by more users more often. Thus the ﬁnal products that are obtained are the high demand products.
<br/>
<ul><li>Model:</li></ul> Once the information about the products being re-ordered in high demands was obtained now the information of every user was extracted by merging the orders data-set to get the user-id information. Once the dataset was merged the number of times each product was ordered by each customer was extracted by grouping on user-id and product-id and converted to a single row which also gives us a vector for each user indicating the products that they had bought. A user-user similarity matrix was generated using cosine similarity as it gives us how overlapping the two vectors are. A product user matrix was also generated using to get a vector for each product which indicates which customers ordered that speciﬁc product. Thus the product user matrix and user-user similarity matrix is used to recommend products to a speciﬁc user by performing a dot product between the item-user similarity and a vector that is the list of users similar to that user. Performing a dot product between the user-user similarity vector and product-user matirx will generate a score.The userusere similarity matrix consist of a score of how similar a user is to other user the score ranges between 0-1, and the item-user matrix contains information about the users that bought that product thus when a dot product is done between the user-user vector and the item-user matrix, this generates a score which indicates how likely the products bought by the list of users are similar to that of the users that are similar to the user for which the recommendation is being done for each product, thus the product with max score will be the one which will be recommended to the user.
<br/>Thus the same procedure is implemented as a code which is present in RECOMMENDATION_MODEL.ipynb.
<p align="center">
<img src="https://user-images.githubusercontent.com/31769827/48950295-ae00ff80-ef60-11e8-8cea-19fcb9a72363.png" width="550" height="400">
</p>
</ul>

<br/>
<br/>
 The supervised learning algorithm performed well especially the MLP model but with further improvement with the hardware resources the models accuracy could be increased and training the model on a distributed system would in-turn help to reduce the amount of time taken to train the model. But the major problem that was faced when working on the project was to validate the model that uses collaborative ﬁltering and the lack of proper hardware resources. Even though that the model could not validated inferences could be made from the models prediction that it worked pretty well, as it recommended the products that the other users bought who were similar to the current users for which recommendation is being made.


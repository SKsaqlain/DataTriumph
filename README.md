# DataTriumph

<b>Team Members:</b> 
<ul>
<li><b>SK SAQLAIN MUSTAQ.</b></li>
<li><b>SUMAIR AHMED SHARIFF.</b></li>
</ul>
The given repository was created as a part of 5th Semister Data Analaytics Project PESU.


Market basket analysis is based upon the identiﬁcation and analysis of purchasing patterns of the customers it helps in scientiﬁc decision support for retail market by mining association rules among items people purchased together. Mining purchasing patterns allows retailers to adjust promotions, store settings and serve consumers better.The process involves an analysis of historic data and based on that analysis to predict the future occurrences or events.In this paper we have proposed multiple model usig k-nn,SVM, MLP to test whether can supervised learning algorithmn can be used to recommend items to users and also implemented a model that would predict whether the item will be reordered or not, using logisticregression algorithm which was also testted witha NN model to check which model performed better and and also a recommending system that will recommend products to customer based on collaborative ﬁltering and using the products which have been re-ordered multiple times that is high demand. 

<br/>
<br/>
<ul><li>HARDWARE REQUIREMENTS:-</li></ul>
<ul><li type=1>python3</li><li type=1>MINIMUM 18gb OF RAM</li></ul>
<br/>
<br/>
<ul><li>PROPOSED APPROACH:-</li></ul>
As most of the approaches uses Associative rules mining and Apriori based methods thus majority of the time is consumed in generating the rules. 
<ul><li type='A'><b>Data processing:-</b></li><ul> 
The transactions that were present in the dataset were in a single column and not in a basket format thus the dataset was processed to get all the items that is ordered by a single user/transaction, and in-order to model the problem with a supervised learning algorithms, each transaction was further processed, thus the code to processed the data is present data-processing.ipynb. 
<ul><li type='A'><b>Recommending next items using supervised learning approach :-</b></li><ul>
 <ul><li> k-nn:</li></ul>K nearest neighbors is a simple algorithm that stores all available cases and classiﬁes new cases based on a similarity measure (e.g., distance functions). A k-nn model was trained with the above mentioned processed data to predict the next item in the transaction, the model was ﬁt with the processed data distance measure being RMSE .
  

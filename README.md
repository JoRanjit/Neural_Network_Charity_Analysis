<h2> :bank: Neural_Network_Charity_Analysis </h2>

#### Alphabet Soup’s business team has collected a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset  are a number of columns that capture metadata about each organization, such as the following: 
<h4> </br>

* EIN and NAME—Identification columns
* APPLICATION_TYPE—Alphabet Soup application type
* AFFILIATION—Affiliated sector of industry
* CLASSIFICATION—Government organization classification
* USE_CASE—Use case for funding
* ORGANIZATION—Organization type
* STATUS—Active status
* INCOME_AMT—Income classification
* SPECIAL_CONSIDERATIONS—Special consideration for application
* ASK_AMT—Funding amount requested
* IS_SUCCESSFUL—Was the money used effectively </h4>
<h4> This project will use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup</h4>

----------------------------------------------------------------------------------------------------------------------------------------
<h3> :house_with_garden: AlphabetSoupCharity </h3>

 #### As part of the design of this model:
 <h4> 1. Columns EIN and NAME were dropped.</br>  
 2. If the count of unique APPLICATION_TYPE values were less than 500, they were grouped as 'OTHER'.</br>
 3. If the count of unique CLASSIFICATION values were less than 1883, they were grouped as 'OTHER'.</br>
 4. All categorical variables were converted using OneHotEncoder method.</br>
 5. After merging the encoded data to the dataframe, all the original categorical variable columns are dropped.</br>

![merged_df]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/mergedDataframe.PNG)

 6. Next the pre-processed data are separated into 'Features' and 'Target', Scaled and then finally split into 'Train' and 'Test' sets.</br>
    * Target : values of 'IS_SUCCESSFUL' column.
    * Features: values of all other columns in the dataframe.
    
 ![train_test_splt]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/train_test_split.PNG)
 
 7. A Tensorflow Keras Sequential Model is created with:
      * 2 hidden layers - 80 and 30 nodes.
      * Fitted with 100 epochs.
         
 8. Model is compiled and evaluated -
      * 1st without checkpoints
      * 2nd with a callback that saves the model's weights every 5 epochs.
      * Results saved and exported to AlphabetSoupCharity.h5
 #### :triangular_flag_on_post: Model's Loss : 0.5583, Accuracy: 0.7261
![L&A1]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/Charity_L%26A.PNG)
 </h4>
 
 ----------------------------------------------------------------------------------------------------------------------------------------
 <h3> :house_with_garden: AlphabetSoupOptimization </h3>
 
 #### As part of this model - steps 1 through 6 were repeated as above with a few changes:
 <h4>
 * If the count of unique CLASSIFICATION values were less than 4800, they were grouped as 'OTHER'.</br>
 
7. A Tensorflow Keras Sequential Model is created with:
      * 2 hidden layers - 50 and 30 nodes.
      * Fitted with 200 epochs.  
8. Model is complied and evaluated -
      * With a callback that saves the model's weights every 5 epochs.
      * Results saved and exported to AlphabetSoupCharity_Optimzation2.h5
 #### :triangular_flag_on_post: Model's Loss : 0.5693, Accuracy: 0.7212
 ![L&A2]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/optimization_L%26A.PNG)
 </h4>
 
 ----------------------------------------------------------------------------------------------------------------------------------------
 
 <h3> :house_with_garden: AlphabetSoupOptimization - attempt #2 </h3>
 
 #### As part of this model - steps 1 through 6 were repeated as 1st model:
<h4> 
7. A Tensorflow Keras Sequential Model is created with:
      * 3 hidden layers - 80, 50 and 30 nodes.
      * Fitted with 100 epochs.  

 8. Model is compiled and evaluated -
      * With a callback that saves the model's weights every 10 epochs.
      * Results saved and exported to AlphabetSoupCharity_Optimzation3.h5
 #### :triangular_flag_on_post: Model's Loss : 0.5722, Accuracy: 0.7230
![L&A3]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/optimization3_L%26A.PNG)
 </h4>
  
 ----------------------------------------------------------------------------------------------------------------------------------------
 
 <h3> :house_with_garden: AlphabetSoupOptimization - attempt #3 </h3>

 #### As part of this model - steps 1 through 6 were repeated as 1st model, except a few changes:
<h4> 
  *  Columns EIN,NAME and STATUS were dropped. </br>
  *  If the count of unique CLASSIFICATION values were less than 4800, they were grouped as 'OTHER'.</br>  
  
7. A Tensorflow Keras Sequential Model is created with:
      * 2 hidden layers - 80 and 30 nodes.
      * Fitted with 100 epochs.  

 8. Model is compiled and evaluated -
      * With a callback that saves the model's weights every 10 epochs.
      * Results saved and exported to AlphabetSoupCharity_Optimzation4.h5
 #### :triangular_flag_on_post: Model's Loss : 0.5650, Accuracy: 0.7231
![L&A3]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/optimization4_L%26A.PNG)
 </h4>
  
 ----------------------------------------------------------------------------------------------------------------------------------------
 
 <h3> :house_with_garden: AlphabetSoupOptimization - attempt #4 </h3>

 #### As part of this model - steps 1 through 6 were repeated as 1st model, except a few changes:
<h4> 
  *  Columns - EIN,NAME,STATUS and INCOME_AMT were dropped. </br>
  *  If the count of unique APPLICATION_TYPE values were less than 1000, they were grouped as 'OTHER'.</br>
  *  If the count of unique CLASSIFICATION values were less than 1800, they were grouped as 'OTHER'.</br>  
  
7. A Tensorflow Keras Sequential Model is created with:
      * 4 hidden layers - 100,80,30 and 10 nodes.
      * Fitted with 200 epochs.  

 8. Model is compiled and evaluated -
      * With a callback that saves the model's weights every 10 epochs.
      * Results saved and exported to AlphabetSoupCharity_Optimzation5.h5
 #### :triangular_flag_on_post: Model's Loss : 0.5770, Accuracy: 0.7279
![L&A3]( https://github.com/JoRanjit/Neural_Network_Charity_Analysis/blob/main/Captures/optimization5_L%26A.PNG)
 </h4>
  
 ----------------------------------------------------------------------------------------------------------------------------------------
 
 <h3> :round_pushpin: SUMMARY </h3>
 
 ----------------------------------------------------------------------------------------------------------------------------------------
 
 <h3>
  * With the given amount of data in this dataset, even after 5-6 models - it was hard to achieve the 75% Accuracy. </br>
  * After 6 attempts the best Accuracy achieved is with the last attempt which gave 0.7279%. </br>
  * In order to acheive 75% or more Accuracy : </br>
       <i> _ The model needs a larger dataset to be used for training.  </br>
        _ The model can also use more impactful Features in the dataset to get more accurate predictions.  </br>
        _ The model could also be designed using other activation functions like Tanh or LeakyReLu.  </br></i>
 </h3>

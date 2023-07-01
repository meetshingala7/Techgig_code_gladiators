# Techgig_code_gladiators
Techgig Code Gladiators 2023<br>

<h2>Brief Description of the Problem at hand</h2> ​
<h4>
In this problem, the data set has columns 'IS_HCP'  and 'TAXONOMY' which we have to predict using the other 13 features provided in the data set. The most promising features that could be used are 'USERCITY', 'URLS' and 'KEYWORDS'. This is a problem of classification.​
<br>

For the Machine Learning Algorithms, I used a stacked regression and base models were ensemble methods of Gradient Boost and Random Forest and the final classifier as Random Forest for better accuracy for the Binary Classification problem of 'IS_HCP' and Random Forest classifier for the 208 classes of 'TAXONOMY's.​

​

Mean Squared Error (IS_HCP) : 0.00932475569184801​
<br>
Accuracy (IS_HCP): 98.74045466514526%​
<br>
​

Accuracy (TAXONOMY): 81.90994470288774%​
<br>
​<h2>Approach</h2>
The 'URLS' provided here have the keywords extracted from them. Thus, we do not need to deploy a web scraper to extract the keywords. This reduces our task significantly. ​

​

We first have to ensure that are no missing values, and plot some essential graphs to find any outliers and the distribution of the data, I have depicted my plots in the Git-hub Readme File.​​

​

Approach for data cleaning of all 'NaN' values:​​

1.      Fill All Zip-code Values to Zero to denote No Zip-code present​​

2.      Fill All the missing USERCITY values to Neutral as there is no specification of them.​​

3.      Fill all the missing TAXONOMY values to 'None' because when we compare the TAXONOMY column with  IS_HCP we find that for all the 0.0 values in IS_HCP column reflected as 'NaN' in TAXONOMY and we can say for the URL searched the person user is not an HCP.​

​The keywords are present in the format separated by '|' thus we have to split the whole string into a list of strings that will be our individual keywords. After getting all the keywords individually, it is important that we find and only keep the keywords that are common among the testing data and the training data as part of feature engineering.​

<br>
Thus, I eliminate the non-common keywords and keep the ones that are the features for the classification. I join words that are one whole continuous phrase like anxiety and  disorders is represented as "anxietydisorders" are not treated separately by TFIDF vectorizer,​ Once, this is done, we convert all the alphabets to lower case to avoid the same word for e.g. "Anxiety" and "anxiety" as different keywords.​

After this, We perform the process of stemming using snowball stemmer and stem the strings to a shorter version for faster computing.​
<br>
After stemming we vectorize the string data with TFIDF Vectorizer. For the Machine Learning Algorithms, I used a stacked regressor and base models were ensemble methods of Gradient Boost and Random Forest and the final classifier as Random Forest for better accuracy for the Binary Classification problem and Random Forest classifier for the 208 classes of 'TAXONOMY's.​

​

<br>

![channeltype_df](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/44a57cf2-f9b4-4b7c-afc2-2cc808e0d77e)

<br>From the above image it is clear that all the data is serched from Web Browser hence, we will The column will be of no help for training<br><br><br>

![channeltype_dft](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/2fbb096c-057d-4dbf-a693-6b2e8151bacd)

<br>From the above image it is clear that all the data is serched from Web Browser hence, we will The column will be of no help for training
<br><br>
We will check for devices if that column is of any help
But as we see that this the count for each of them is very high and thus will not help is in classifying <br>
For training Data<br><br><br>

![devicetype_df](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/ffd58bf8-f001-483b-8735-5f3cc831f2cb)

<br>For testing Data<br><br><br>

![devicetype_dft](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/8691fc97-f2ef-4d03-a3ed-ecea706d69af)

<br><br><br>
The below mentioned graph shows how the length of keywords is spread out in the training data set<br><br><br>
![lengthoflist_df](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/faf42858-5385-41ac-84d6-6583e2053f76)
<br><br>The below mentioned graph shows how the length of keywords is spread out in the training data set<br><br><br>
![lengthoflist_dft](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/99313f49-2094-49ea-9725-eb93bef8e446)
<br>The below mentioned graph represents how the data spreads acrooss the cities for the testing dataset<br><br>
![usercity_df](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/8e017efb-f039-4352-8dff-f9a71cd3fb5e)
<br>The below mentioned graph represents how the data spreads acrooss the cities for the testing dataset<br><br>
![usercity_dft](https://github.com/meetshingala7/Techgig_code_gladiators/assets/123167152/d4981c8a-89e1-41d7-a5da-7b378fce18bb)

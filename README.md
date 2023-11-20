# Spam Message Detection : Project Overview  
* Developed a method to identify spam messages(AUC=0.99), aiding recipients in avoiding deception.  
* Utilized NLTK for tokenization and Word2Vec for data preprocessing.  
* Optimized models using Random Forest, Catboost, and LightGBM, and achieved final results with LSTM and RoBERTa.  



## Let's delve deeper!

> Table of Content:
1. [Part 1: Exploratory Data Analysis](#part1)
2. [Part 2: Vectorize the Text](#part2)
3. [Part 3: Build ML Model and Evaluate](#part3)
4. [Part 4: Build LSTM/RoBERTa](#part4)

<a id='part1'></a>
## Part 1: Exploratory Data Analysis

**This is a dataset with anomalies. To begin, let's first take a look at the data and examine the proportion of anomalies.**  
Here's the head of our data.  
<img width="311" alt="image" src="https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/7d376c48-562f-44f5-80c2-6cb70e8faba9">

And here is a bar chart depicting the distribution ratio of these two types of messages.  
![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/1bf5031e-dafc-4c40-b8e9-e952be7c7311)

**We can now examine the distribution of ham and spam messages based on vocabulary size.**   
**It appears that the vocabulary size for spam messages is relatively concentrated and not very extensive.**  

![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/2f088e84-bf2d-43d4-a400-ac1562b90130)

### Common word analysis: 
Examine the most frequently used words in "spam" and "ham" messages.

We find that the most words in spam messages is call and free. It could indicate that in spam messages, there are more references to calling or attempt to deceive people with promises of free service.  

![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/ade8e631-1dc0-479d-867d-f46b54bf51d1)

<a id='part2'></a>
## Part 2: Vectorize the Text
Firstly, I utilized NLTK for tokenization, followed by vectorization using a pre-trained Word2Vec model. Afterward, I employed TF-IDF to weight each word in the sentence, obtaining a weighted average vector.  

<a id='part3'></a>
## Part 3: Build Model and Evaluate
Following that, we can utilize the pre-weighted vectors for various machine learning tasks.
Since it's imbalanced data, we evaluate the model with AUC curve and precision-recall curve.

**Here's the Decision Tree model**  
![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/91e31527-2d16-4563-bf99-8e75966cd2c7)

**Here's the Random Forest model**  
![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/cbc39851-984e-47d8-8d37-278777c478db)

**Here's the SVM model**  
![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/4e95a79f-b724-4d4b-bda3-4d063888e3b3)

**Here's the Catboost model** 


<img width="387" alt="image" src="https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/36987c06-6979-4409-b475-c235e8075471">

**Here's the LightGBM model** 


<img width="374" alt="image" src="https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/33e768a8-c485-451a-89ae-c374a84ae0e0">

<a id='part4'><a/>
## Part 4: Build LSTM/RoBERTa
Due to the textual nature of our data, and the fact that sentences have context, I will proceed to build models using LSTM and RoBERTa.   

Let's see the result of LSTM model.  
![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/28a84e26-a907-4e28-961e-58f0959c46f2)

And this is the result of RoBERTa model.  
![download](https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/9064709b-24c9-4f31-95c5-440a4c10bc86)

It's evident that through model tuning and method enhancements, we've ultimately obtained a model with an AUC close to 1.  

**And we can randomly generate some messages to observe if the model can predict them correctly.**  
Let's see the result!  


<img width="770" alt="image" src="https://github.com/Elvis-YAL/Spam-Message-Detection/assets/40426433/d1744e3a-dab8-4559-89fa-1d73d3af7c60">

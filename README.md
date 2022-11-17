# NLP & Sentiment Analysis of Products Reviews


![622f5ab3c267051b690b6e6c_NLP Tools_Thumbnail](https://user-images.githubusercontent.com/78451214/201503092-6020e3f0-25e8-41a6-9954-b8c2ee1c1e0c.png)

<pre>
Code  : <a href=https://github.com/DATA-606-FALL-2022/Data606_Ling/tree/main/Code> Notebook </a> </a>
Data Source  : <a href=https://github.com/DATA-606-FALL-2022/Data606_Ling/tree/main/Data> Data </a> </a>
Power Point:  <a href=https://github.com/DATA-606-FALL-2022/Data606_Ling/blob/main/Sentiment%20Analysis%20-%20%20Amazon%20review.pptx>Presentation</a>
Video: <a href=https://youtu.be/rzPBnFjj4vA>Youtube</a>

</pre>
Sentiment analysis is the method of analyzing consumer sentiment using natural language processing, text analysis, and statistics. Many companies are aware of their customers’ feelings — what they’re doing, how they’re saying it, and what they mean. Instead of reading word by word and trying to figure out its sentiment, nowadays with the advance of machine learning, human just let the machine read news or comments for us and it will answer the sentence’s sentiment or meaning in the faster time.

My mission in this project is to utilize machine learning to automatically predict whether the given comment is positive or negative. This application helps reduce the significant time that the marketing initiatives read every comment and figure out its sentiment.


<img width="541" alt="sentiment-analysis-machine-learning-techniques" src="https://user-images.githubusercontent.com/78451214/201502904-3e5d58f9-c784-4a2d-bcd7-9f4c7b2fda51.png">

## Data Set 

### Overview
The dataset has been collected from https://data.world/datafiniti/consumer-reviews-of-amazon-products website and is a .csv file with the size of 365.82 MB. This is a list of over 1,500 consumer reviews for Amazon products like the Kindle, Fire TV Stick, and more provided by Datafiniti's Product Database. The dataset includes basic product information, rating, review text, and more for each product.

### Data Elements
The images on the bottom shows the 27 columns within the dataset, along with the description for each. 
Out of the 27 elements, the ones that will be used in our project are Features:
- reviews.date
- reviews.text
- reviews.rating

![1](https://user-images.githubusercontent.com/78451214/202548211-d2250d5e-f32e-4eb5-a641-7a69446b4c63.png)

## Data Cleaning and Preprocessing
Data preprocessing involves the transformation of the raw dataset into an understandable format. Preprocessing data is a fundamental stage in data mining to improve data efficiency. The data preprocessing methods directly affect the outcomes of any analytic algorithm.

### 1. Data overview
  - 1.1 Import dataset and libraries 
  
  - 1.2 Check missing values
      
   Check and remove all rows that contain missing values to avoid classification or regression error.
#### 2. Text preprocessing

  - 2.1 Remove none text and special character
    
   Text data might include website link, hashtags etc… These things better be removed from the text before we run the model.

  - 2.2 Convert all text to lowercase
   
   To avoid the mistake during the training that the word like “We” and “we” might get learn differently, we turn all words with capital letter into lower cases.
  - 2.3 Tokenization
    
   One sentence consists of many words, but not all words are important. To analyze each word, we need to split words into single word for each sentence.
  - 2.4 Remove stopword
    
   Stopwords are words such as ‘I’, ‘we’, ‘my’, ‘you’, ‘own’, ‘only’ etc… These words are not likely to represent particular meaning. The model might consider this as noise, so we remove it as to keep noise level down.

  - 2.5 Lemmatization vs. Stemming
  
   Stemming is the process of producing morphological variants of a root/base word. Stemming programs are commonly referred to as stemming algorithms or stemmers. In contrast to stemming, lemmatization looks beyond word reduction and considers a language’s full vocabulary to apply a morphological analysis to words.

### Data Visualization
Data visualization is the practice of translating information into a visual context, such as a chart or graph, to make data easier for the human brain to understand and pull insights from. The main goal of data visualization is to make it easier to identify patterns, trends and outliers in large data sets.

#### Standardization the Ratings
This is an important preprocessing phase, we are deciding the sentiment of review based on the overall score. If the score is greater than 3, we take that as positive and if the value is less than 3 it is negative If it is equal to 3, we take that as neutral sentiment

![Screen Shot 2022-11-17 at 3 24 56 PM](https://user-images.githubusercontent.com/78451214/202552408-ee11ff25-f41b-4a52-a678-f27e239c2f84.png)

### EDA

   1. Check number of words per review
       
       ![Screen Shot 2022-11-17 at 3 27 07 PM](https://user-images.githubusercontent.com/78451214/202552845-f4375943-a117-493e-bd68-5364318bb9b5.png)
       ![Screen Shot 2022-11-17 at 3 27 30 PM](https://user-images.githubusercontent.com/78451214/202552847-11d169e6-0d3c-4225-ac3a-7d9da69b6edf.png)
      
   Insight: Negative reviews are longer than positive and neutral reviews
   
   2. Sentiment review counts over year
  
   ![Screen Shot 2022-11-17 at 3 33 05 PM](https://user-images.githubusercontent.com/78451214/202557461-f4d544f6-4c48-42c5-b9ac-5dcc301a7231.png)

Insight: From the plot we can clearly see the rise in positive reviews from 2014. Reaching its peak around 2016 then it start going down. Negative and neutral reviews are very low as compared to the positive reviews
   
   3. Reviews count distribution 
   
   ![Screen Shot 2022-11-17 at 3 54 47 PM](https://user-images.githubusercontent.com/78451214/202557826-5a3ad435-8fa8-4817-99cc-17aa3589a6e1.png)

  Insight: More reviews at the starting of a year
   
   4. Creating word cloud 
As a distribution of the text in a visualization way, a word cloud displays the words in different sizes, indicating the frequency of the each word in the text. Looking at the word cloud, it shows that the reviews are related to the electronic products such as: "Keyboard", etc. Some words are related to the customers experiences, such as: "great", "love", etc.

![Screen Shot 2022-11-17 at 3 56 14 PM](https://user-images.githubusercontent.com/78451214/202558074-c4f22a86-e1b5-432b-ad1a-81aaf4caeb88.png)




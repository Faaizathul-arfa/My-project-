# Fake news Detection
 Batch 2.
 
 By : Faaizathul Arfa

## Problem Defination:

Developing a machine learning project to distinguish fake news from a real one.we can use supervised learning to implement the model.Using sklearn, building a TfidfVectorizer on our dataset. Then,initializing a PassiveAggressive Classifier and fit the model. In the end, the accuracy score and the confusion matrix tell us how well the model fares.
 
## Introduction:

The topic of fake news detection on social media has recently attracted tremendous attention. The basic countermeasure of comparing websites against a list of labeled fake news sources is inflexible, and so a machine learning approach is desirable. Our project aims to use detect fake news directly, based on the text content of news articles.
    
 
## Steps involved:
 
 1. Analysing the dataset and cleanig the data.
 
 2. Data preparing.
 
 3. Building the machine learning models.
 
 4. evaluating the models for better accuracy.
 
### 1. Analysing the dataset and cleanig the data

Dataset is in filename.csv form is read and displayed to get the idea of labels .first few lines of the file are displayed 
```
df=pd.read_csv('/content/news.csv')
df.head()
```
```
labels=df.label
print(labels.head())
```
### 2.Data preparation
splitting dataset arrays into two subsets.that is train and test set.This for training the model and test the accuracy.The test size is taken as 0.33

```
from sklearn.model_selection import train_test_split
X=df['text']
y=labels
X_train,X_test,y_train,y_test=train_test_split(X,y,test_size=0.33)
```
Initializing the TfidfVectorizer with stop words with maximum document frequency 0.8  .stopwords are the unneccasery words that needs to be filtered before processing natural langauage data.The job of TfidfVectorizer is to turn a collection of raw data into a TF-IDF matrix

next, fit and transform the vectorizer on the train set and transform the vectorizer on the test set 
```
from sklearn.feature_extraction.text import TfidfVectorizer
tfidf_vectorizer=TfidfVectorizer(stop_words='english', max_df=0.8)
tfidf_train=tfidf_vectorizer.fit_transform(X_train) 
tfidf_test=tfidf_vectorizer.transform(X_test)
```


### models used for classification:
### 1.

You can use the [editor on GitHub](https://github.com/Faaizathul-arfa/my_project/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Faaizathul-arfa/my_project/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

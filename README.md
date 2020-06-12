# NLP and Pipelines
 
Natural language processing is one of the fastest growing fields in the world.This Repo begins with an overview of how to design an end-to-end NLP pipeline where you start with raw text, in whatever form it is available, process it, extract relevant features, and build models to accomplish various NLP tasks. 

NLP Pipelines consist of tree stages:

<p align="center">
  <img src="/imgs/1.PNG" alt="" width="500" height="150" >
 </p>
 
   * **Text Processing**: Take raw input text, clean it, normalize it, and convert it into a form that is suitable for feature extraction.
   * **Feature Extraction**: Extract and produce feature representations that are appropriate for the type of NLP task you are trying to accomplish and the type of model you are planning to use.

   * **Modeling**: Design a statistical or machine learning model, fit its parameters to training data, use an optimization procedure, and then use it to make predictions about unseen data.
   
   
**This process isn't always linear and may require additional steps to go back and forth.**

## Stage 1: Text Processing
In this step we will explore the steps involved in **text processing**, but before, the aquestion of why we need to Process Text or why we can not feed directly, should be answered.


 * **Extracting plain text**: Textual data can come from a wide variety of sources: the web, PDFs, word documents, speech recognition systems, book scans, etc. Your goal is to extract plain text that is free of any source specific markup or constructs that are not relevant to your task.
 
 * **Reducing complexity**: Some features of our language like capitalization, punctuation, and common words such as a, of, and the, often help provide structure, but don't add much meaning. Sometimes it's best to remove them if that helps reduce the complexity of the procedures you want to apply later.


**The following presented the text processing steps to prepare data from different sources:**

 1. **Cleaning** to remove irrelevant items, such as HTML tags
 
 2. **Normalizing** by converting to all lowercase and removing punctuation
 
 3. Splitting text into words or **tokens**
 
 4. Removing words that are too common, also known as **stop words**
 
 5. Identifying different **parts of speech** and **named entities**
 
 6. Converting words into their dictionary forms, using **stemming and lemmatization**

**After performing these steps above, your text will capture the essence of what was being conveyed in a form that is easier to work with.**


### 1. Cleaning: 

In this section I am going to walk through the step of cleaning text data from a popular source - **the web**. You'll be introduced to helpful tools in working with this data, including the [requests library](http://docs.python-requests.org/en/master/user/quickstart/#make-a-request), [regular expressions](https://docs.python.org/3/library/re.html), and [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/).


### 2. Normalization: 

Plain text is great but it's still human language with all its variations. we'll try to reduce some of that complexity.  **Lowercase conversion** and **punctuation removal** are the two most common text normalization steps.  

*  In the English language, the starting letter of the first word in any sentence is usually capitalized.  While this is convenient for
a human reader, from the standpoint of a machine learning algorithm, it does not make sense to differentiate between them. (for example Car,car, and CAR), they all mean the same thing. Therefore, we usually convert every letter in our text to a common case,usually lowercase, so that each word is represented by a unique token. 

*  you may want to remove special characters like periods, question marks, and exclamation points from the text and only keep letters of the alphabet and maybe numbers. This is especially useful when we are looking at text documents as a whole in applications like document classification and clustering where the low level details do not matter a lot. 

* Is it better to just replace punctuation characters with a space, because words don't get concatenated together, in case the original text did not have a space before or after the punctuation.

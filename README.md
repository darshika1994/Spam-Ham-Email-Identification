# Spam-Ham-Email-Identification
This is a document classification project to classify spam vs ham. I will construct a spam filter to classify text message as ham or spam. 
STEPS TO BE FOLLOWED -------------------------------->>>>>>>>>>>>>>
SPAM-HAM GITHUB (DARSHIKA)
1. Loading data (category - target variable(spam/ham) & Message)

2. EDA --->
	a. Analysis of target variable(groupby/bar graph)
	b. Create a seperate spam/ham dataframes

3. Processing ---> (Part - I)
	a. def wordCount(text) - contains info a8 PROCESSED LENGTH
		- text lower case
		- punctuation remove[re.escape]--> (then replace them text using re.sub)
		- stop words remove and len(w)>3 (length of words)
		- apply the above steps on spam and ham to get len using split and processed_len using wordCount function
                  (use lambda expression)

	b. Count the no. of punctuation in spam and ham
		- by using apply(lambda l1: sum([1 for x in l1 if x in set(string.punctuation)])
	
4. Conclusion of Processing step - will be having spam and ham dataframes with len, processed_len, and count of punction

5. Text length distribution analysis 
		- describe (spam_df[['len', 'processed_len']].describe()) and (ham_df[['len', 'processed_len']].describe())
		- len plot 4 histograms (ax,ax1,ax2,ax3) : spam vs len, spam vs proc_len, ham vs len, ham vs proc_len

6. Processing ---> (Part - II)
	a. def tokenize(text)
		- punctuation remove[re.escape]--> (then replace them text using re.sub)
		- TOKENS STATEMENT :
			-tokenize the text --> remove stop words --> convert it in lower and remove len(w)>3 --> re.search('[a-zA-Z]', w)
		- use .map(tokenize) on spam and ham dataframes 

7. Most Common Words - (what is the most 10 common words in spam and ham texts)
	- create a NEW dataframe as spam_count_df and ham_count_df which will store two columns(word and count)
	- plot barplot (ax,ax1) - one for spam_count_df and another for ham_count_df

8. World Cloud - World cloud is just a better view of Most Common Words (pictorial)
	- Step 1 : Create spam_words_str by joining spam_words (will return us a paragraph of all the spam words) and similarly do for ham
	- Step 2 : Create spam_word_cloud by calling WorldCloud().generate(spam_words_str) and similarly for ham
	- Step 3 : Create a pictorial view (ax,ax1) for spam and ham words - (by imshow(spam/_word_cloud)) & similarly for ham

9. Modelling - 
	- 1. Create tf-idf vectorizer (by this, FEATURE and TARGET would be obtained which would be used for training models) 
		(tf-idf vectorizer needs to be made after performing all the above 8 steps only)
	- CREATE MODELS

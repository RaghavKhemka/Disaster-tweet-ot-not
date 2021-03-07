# Natural Language Processing with Disaster Tweets
Kaggle's tweet disaster problem - https://www.kaggle.com/c/nlp-getting-started/overview

# Summary of the process
-The dataset has tweets with their labels on wheather the tweet is regarding a disaster or not.
-All the tweets on disaster are labeled as 1 and others are labeled as 0.

## PREPROCESSING
-The tweets are very raw and contain unwanted symbols which will create extra tokens for same words and meaningless words. 
<br />-Any word which contains symbols like ['@','%','&'] is removed because they mostly meaningless adding noise to the data.
<br />-So all the symbols like ['-',':','.','?',')','('] are removed from each word of each of the sentences.
<br />-The Hashtags cannot be removed because they have useful information. So only the ('#') symbol was removed and the word retained.
<br />-All the words which are links to some website or blog are replaced by a unique word('http_link') so that our program can identify them as a LINK.
<br />-Any word which is longer than 13 characters is removed as they are generally jibber-jabber and meaningless.
<br />-All non ASCII characters and integers are also removed.
<br />-The top 2000 commonly occouring words are taken for tokenizing.
<br />-32 dimensional Embeddings are created for each of the words.
<br />-Each sentence is limited to a length of 25 words. Smaller sentences are padded with zeros at the end. (POST TRUNCATING).
<br />
## MODEL
<br />-A sequential model in Keras in made using tensorflow.
<br />
<br />-First layer is the input layers which takes a sentence (25 words and 32 dimension embedding for each of them).
<br />-Next is a Biderictional LSTM layer with 32 Neurons.
<br />-Dropout of 20 Percent is done in the next layer to avoid overfitting.
<br />-The output layer is a single neuron layer with sigmoid activation to give an output between 0 and 1.
<br />

##   Validation accuracy of around 90% was reached with this process.


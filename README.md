# Events_Analysis

Libraries used:

1. Pandas
2. Numpy

Built-in Modules used:

1. Collections

Packages

1. Tensorflow
2. Keras Api

Neural Network---> LSTM

APPROACH:

Collecting data from Tweets(using Advanced Search)
-> Used snscrape for scraping, fetching tweets

-> Data Cleaned, emojis removed, removed all words starting with @, http:// as these don’t carry information and hamper the processes like tokenization , word embedding and all.

-> All those tweets where a person is assumed to not attend the event, labeled as 0, and others labeled as  1 accordingly. Data shuffled. (Data also shuffled while training in ahead steps)



SOLVING:

-> Use Word Embeddings. With help of word embeddings, we convert words into vectors. 

-> There are built-in functions to do so, but if want to go deep into architecture, Positional embedding, and all is done, for example, position of words change the meaning of sentence and can confuse. All this is taken care by these built-in functions.(Dot product of vectors and mathematics involved) 

-> Every sentence is hereby converted into a vector, with each word having certain value, determined by how many times it occurred in dataset, where and when used, all done by code itself.

-> Padding is done, what if one of the statements is 146 words long and other is 200 words long. We choose the pad length of 200, so that when put into training, The remaining 54 words will be replaced by '#' most probably, so that same length of 'data' is fed into.




MODEL BUILDING


-> Using tensorflow, start by loading Sequential, i.e. stack of layers, where there is one input and one output tensor.

-> Add Embedding Layers(reason explained above)

-> Add Dropout Layer to drop certain neurons by giving parameters, mostly to avoid overfitting.

-> We then insert LSTM cell.(Not giving depth- explanation of how the architecture is used). It is used so as to store information for longer period of time. It has other uses as well, for example, weights getting updated becomes easier.

-> Model is then trained by using commands which are genrally used. 

-> Using h5py , we save the model for further use, so that next time, we train another model, we can use the weights directly and make predictions.

-> We get an accuracy of approximate 91% to 92%



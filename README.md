# RNNResearchSentimentAnalysis
This repository contains the code that is being used in part of my research project.

The Experiment investigates the effect of non-stop words on the state of RNN.

<b>Dataset</b>

We have used 2 synthetic sentiment analysis datasets. Each sentence is 10 words long.
The vocubulary has 100 words (0-99) where words [80,89] are positive, [90,99] are negative, [0,79] are stop words.

Label 1 represents Positive sentiment while Label 0 represents Negative sentiment.

1) <b>Dataset1:</b>
   train_count10 = 15000 instances, val_count10 = 2000 instances, test_count10 = 3000 instances.
   A sentence with number of positive words greater than or equal to number of negative words is assigned to a positive class(1) otherwise it is assigned to a negative class(0).
   
2) <b>Dataset2:</b>
   train_first10 = 15000 instances, val_first10 = 2000 instances, test_first10 = 3000 instances.
   
   A sentence in which the first non-stop word is negative is assigned to the negative class(0) otherwise it is assigned to the positive class(1).
   
<b> Model </b>
  
We used pytorch to built vanilla RNN and trained it over the training dataset and then evaluated it against validation set.

We used single layer unidirectional RNN with different number of hidden units. The equations are similar to the ones mentioned in pytorch documentation of basic RNN. It has fully connected layer as the last layer. Adam optimizer and tanh activation function is used. The cross entropy loss function used.

The random seed is 2109, learning rate is 0.001, patience parameter is 4, input units are 10 and output units are 2, the maximum epochs are 150.

The **ModelCount8.pt** was trained on Dataset1 with 8 hidden units. The accuracy on training dataset (train_count10) and validation dataset (val_count10) is **97.96%** and **98.25%** respectively.

The code used is written in **SentimentAnalysisCode.ipynb**. **ModelCount8.pt** has the saved model, **AccuracyCount.txt** has the loss and the accuracy after each epoch, **ResultCount8.json** has the model parameters.

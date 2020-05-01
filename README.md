# Speaker-fluency
The model classifies audio clips fluency level.
In this work we are interested in comparing diﬀerent classiﬁcation frameworks,
namely, multilayer perceptrons, convolutionalneuralnetworks, recurrentneuralnetworks, support vector machines and random forest. 
The main goal here is to test each model classiﬁcation accuracies as we vary the number of features extracted.

The proposed multilayer perceptron architecture hastwo hidden layers comprising 512 x 512 neurons followed by an output layer 
consisting of three neurons (one representing each ﬂuency class). 
Each neuron within the hidden layers uses the relu function as the activation function. 
For the output layer, we implement the softmax function to convert the output into class probabilities. 
Finally, the predicted label is the class with the highest probability. The convolutional neural network architecture has four hidden 
layers, the ﬁrst two have 64 convolution ﬁlters and the following two have 32 convolution ﬁlters. The output layer consists of three 
neurons corresponding to our three classes and similarly to the multilayer perceptron, the activation function of the hidden layers is 
the relu and for the output layer is the softmax function. The recurrent neural network architecture is a longshort-therm-memory (LSTM) .
It has two hidden layers comprising 256 x 32 neurons and three neurons corresponding to the output layer. This architecture also 
implements the same activation functions as the other two networks. In table 1 we summarize the architectures described above.

Neural Network      Hidden layers    Neurons            Activation 
MLP                     2           512x512x3           relu,softmax 
CNN                     4           64x64x32x32x3       relu, softmax 
RNN                     2           256x32x3            relu, softmax

The other two models are traditional machine learning models. 
One is a support vector machine. This model has a basic construction (similar to the one proposed in the scikitlearn documentation). 
The main hyper-parameter of the estimator that we varied was the regularization parameter C. 3 
The other model uses a random forest classiﬁer. 
This model also has a basic construction in the sense that our python script only initializes the model, trains it and then evaluates 
its performance. 
The single parameter we varied here was the number of estimators (number of trees).4


Nmel = 20 as baseline features and test extra spectral features to see the 

 Conclusions: 
  In this work, we have presented an audio processing system capable of determining the level of ﬂuency of non-native Englishspeakers, 
  taken5snon-overlappedaudiosegmentsfrom the Avalinguo audio set. We have used ﬁve diﬀerent ML models to classify audio segments into 
  low, intermediate or high ﬂuency levels. Each model was capable of classifying audio frames with an accuracy of more than 
  90% (except one classiﬁer that reached 89%). As a ﬁrst step, we have determined that the appropriate number of Mel cepstral coeﬃcients 
  for our data set is 20. Thereafter, with these baseline features, we have added zero-crossingrate, root mean square energy and spectral
  ﬂux features to improve the accuracy of our models. 
  The highest accuracies were reached by SVM and RF, with 94.39% and 93.45%, respectively. 
  The neural networks achieved also remarkable accuracies (MLP 92.52%, CNN 92.75%, RNN 89.01%). 



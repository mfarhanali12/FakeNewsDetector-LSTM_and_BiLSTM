# FakeNewsDetector-LSTM
Fake news Classifier using the LSTM, which classifies whether a news is fake or not 

What is LSTM?
Long short- term memory (LSTM) units are a building block for the layers of a recurrent neural network (RNN). A LSTM unit is composed of a cell, an input gate, an output gate and a forget gate. The cell is responsible for "remembering" values over a vast time interval so that the relation of the word in the starting of the text can influence the output of the word later in the sentence. Traditional neural networks cannot remember or keep the record of what all is passed before they are executed this stops the desired influence of words that comes in the sentence before to have any influence on the ending words, and it seems like a major shortcoming.

### Steps
1.  Preprocess data
2. One_hot encoding
3. Create LSTM model
4. Observe the alteration in shape, flattening and then re-shaping - changes from embedding to flattening - to - dense layer  
5. Observe the total weight matrix size of the LSTM - mathematical verification

Keras provide the function <font color = "Yellow">one_hot</font> to efficiently encode each word in the titles as an interger.  This must be done prior to Word Embedding Index of words located in the Dictionary

### Arguments:  
- sequences  
List of lists where each element is a sequence  
- maxlen  
int, maximum length of all sequences
- dtype  
type of the output sequences
- padding 'pre' or 'post', pad either before or after each sequence.

- sequence() a plain stack of layers where each layer has exactly one input tensor and one output tensor 
- create a Sequential model incrementally via the add() method  the input of the LSTM is always a 3D array (batch_size, time_steps, units)  
- The output of the LSTM could be a 2D array or 3D array depending upon the return_sequences argument. If return_sequence is False, the output is a 2D array. (batch_size, units) If return_sequence is True, the output is a 3D array. (batch_size, time_steps, units) in this case; the return_sequence is false - this is the default, therefore - 2D LSTM outpu

- Describe performance of classificaiton model  tweak to make sure that 'acc' and 'val_acc' and final 'accuracy' are more closer to each other. It is normal for validation accuracy to be lower than accuracy. But ideally, these values should be kept similar range. If validation accuracy is much lower than accuracy, be cautious of over fitting  
- acc' refers to accuracy of what was trained against.  
- 'val_acc' refers to validation set. Note that val_acc refers to a set of samples that was not shown to the network during training and hence refers to how much your model works in general for cases outside the training set.

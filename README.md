# mnist hierarchical rnn
Taken from keras [example](https://github.com/keras-team/keras/blob/master/examples/mnist_hierarchical_rnn.py)
Original paper - [A Hierarchical Neural Autoencoder for Paragraphs and Documents]- https://arxiv.org/abs/1506.01057


Example of using Hierarchical RNN (HRNN) to classify MNIST digits.

HRNNs can learn across multiple levels
of temporal hierarchy over a complex sequence.
Usually, the first recurrent layer of an HRNN
encodes a sentence (e.g. of word vectors)
into a  sentence vector.
The second recurrent layer then encodes a sequence of
such vectors (encoded by the first layer) into a document vector.
This document vector is considered to preserve both
the word-level and sentence-level structure of the context.

### References

- [A Hierarchical Neural Autoencoder for Paragraphs and Documents](https://arxiv.org/abs/1506.01057)
    Encodes paragraphs and documents with HRNN.
    Results have shown that HRNN outperforms standard
    RNNs and may play some role in more sophisticated generation tasks like
    summarization or question answering.
- [Hierarchical recurrent neural network for skeleton based action recognition](http://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7298714)
    Achieved state-of-the-art results on
    skeleton based action recognition with 3 levels
    of bidirectional HRNN combined with fully connected layers.

In the below MNIST example the first LSTM layer first encodes every
column of pixels of shape (28, 1) to a column vector of shape (128,).
The second LSTM layer encodes then these 28 column vectors of shape (28, 128)
to a image vector representing the whole image.
A final Dense layer is added for prediction.

After 5 epochs: train acc: 0.9858, val acc: 0.9864

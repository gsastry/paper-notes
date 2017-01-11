# Title: Reducing the Dimensionality of Data with Neural Networks #
# Authors: G. E. Hinton, R. R. Salakhutdinov #

# Summary

This paper introduces autoencoders, which are a system composed of an encoder
and decoder. The encoder outputs a low-dimensional reduction (compression/encoding)
of the data, and the decoder uses that encoded data to retrieve the data. They
compare autencoders with PCA (a well known technique that finds the orthogonal
directions of greatest variance in the data).

The choice of initial weights is important: if it's close to the solution, then
we can train using SGD and find the solution; but if it's far, it won't converge.

The authors introduce a pretraining procedure that gets around this limitation,
where you represent the black & white images by binary vectors, and train a
RBM: you create "confabulated" images, where each $v_i$ in the input vector is
set to 1 with probability 1/z (logistic function). Then the change in weights
is given by the difference betwixt the fractions of training data and confabulated
data weighted by the learning rate.

This pretraning procedure is clever and intuitive

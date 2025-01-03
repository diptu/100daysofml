# 100 Days of ML
- daily ML Practice

# Certification:

## Convolutional Neural Networks:

### Day 001: Edge Detection
**NxN matrices are convolved by FxF filter/kernel; the output would be (N-F+1) by (N-F+1) matrices.**
- e.g., a 6x6 matrix is convolved by a 3x3 filter; the output would be a 4x4 matrix.
- F should always be odd, e.g., 3, 5, 7...
- This process shrinks the image.
- Information from corner/edge points is discarded.

## Limitation:
- Images shirinks
- Pixels in the edges are considered less than in the middle of the image.

1. **valid convolution**: No Padding
2. **same convolution**: Output image and input image size are equal.
## Padding
- By convention, padding is done with zeros.
**NxN matrices are convolved by FxF filter/kernel with padding of p; the output would be (N+2p-F+1) by (N+2p-F+1) matrices.**
- e.g., a 6x6 matrix is convolved by a 3x3 filter with padding of 1; the output would be a 6x6 matrix.
  - *Valid:* No padding (Image shrinks).
  - *Same:* p = (F-1)/2 (Retain original shape).

### Stride
**NxN matrices are convolved by FxF filter/kernel with padding of p and stride of S; the output would be `floor((N+2p-F)/S) + 1` by `floor((N+2p-F)/S) + 1` matrices.**
- e.g., a 6x6 matrix is convolved by a 3x3 filter with padding of 1 and strided with 2; the output would be a 3x3 matrix.
- e.g., a 7x7 matrix is convolved by a 3x3 filter with padding of 1 and strided with 2; the output would be a 4x4 matrix.
  
### Day 002:One Layer of a Convolutional Neural Network

-if Layer l is a convolution layer with:
  - filter size f<sup>[l]</sup>, padding p<sup>[l]</sup>, stride s<sup>[l]</sup> and no of filters n<sub>c</sub><sup>[l]</sup>
  - if input activation from previous layer is : n<sub>h</sub><sup>[l-1]</sup> x n<sub>w</sub><sup>[l-1]</sup> x n<sub>c</sub><sup>[l-1]</sup>
  - Output: n<sub>h</sub><sup>[l]</sup> x n<sub>w</sub><sup>[l]</sup> x n<sub>c</sub><sup>[l]</sup>
  - n<sub>h</sub><sup>[l]</sup> = floor([(n<sub>h</sub><sup>[l-1]</sup>+2p<sup>[l]</sup> -f<sup>[l]</sup>)/s<sup>[l]</sup> +1])
  - n<sub>w</sub><sup>[l]</sup> = floor([(n<sub>w</sub><sup>[l-1]</sup>+2p<sup>[l]</sup> -f<sup>[l]</sup>)/s<sup>[l]</sup> +1])
  - Size of the each filter: f<sup>[l]</sup>x f<sup>[l]</sup> x n<sub>c</sub><sup>[l-1]</sup>
  - activation: a <sup>[l]</sup> =  n<sub>h</sub><sup>[l]</sup> x n<sub>w</sub><sup>[l]</sup> x n<sub>c</sub><sup>[l]</sup>
  - Weights : f<sup>[l]</sup> x f<sup>[l]</sup>  x n<sub>c</sub><sup>[l]</sup>
  - Bias : n<sub>c</sub><sup>[l]</sup>
  

## Example Convolutional Neural Network:
- if input image Size 39 x 39 x 3,filter size = 3 x 3, n<sub>h</sub> = 39, n<sub>w</sub> = 39, n<sub>c</sub> = 3
- for a **valid** convolution padding, p = 0, if stride s = 1, and we use 10 filters
- output image size 37 x 37 x 10,  n<sub>h</sub> = 37, n<sub>w</sub> = 37, n<sub>c</sub> = 10
- if we now use a 5x5 filter, with stride s= 2 and no padding p = 0, 20 filters
- output image size 17 x 17 x 20,  n<sub>h</sub> = 17, n<sub>w</sub> = 17, n<sub>c</sub> = 20
- if we now apply another a 5x5 filter, with stride s= 2 and no padding p = 0, 40 filters
- output image size 7 x 7 x 40,  n<sub>h</sub> = 7, n<sub>w</sub> = 7, n<sub>c</sub> = 40
-  flatten 7x 7 x 40 = 1960 units and feed to a logistic/softmax unit to predict ŷ


### Day 003: Lnet -5

<p>
    <img src="./lenet.svg" alt="Lnet-5">
    <em>Lnet-5</em>
</p>


### Day 004: Cats vs dogs - classification
https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html

### Day 005: Pretrained models in CNN, Transfer Learning
- https://keras.io/api/applications/
-https://machinelearningmastery.com/how-to-visualize-filters-and-feature-maps-in-convolutional-neural-networks/
- https://colah.github.io/posts/2014-07-Understanding-Convolutions/
- https://colah.github.io/posts/2015-01-Visualizing-Representations/

### Day 001: WordNet, word2vec, word embedding, bilingual word-embedding,CS224N
- https://colah.github.io/posts/2014-07-NLP-RNNs-Representations/
- https://www.youtube.com/watch?v=rmVRLeJRkl4
- https://wordnet.princeton.edu/
- https://www.youtube.com/watch?v=viZrOnJclY0
- https://www.tensorflow.org/text/tutorials/word2vec
- https://www.tensorflow.org/text/guide/word_embeddings
- http://jalammar.github.io/illustrated-bert/
- https://blog.okfn.org/2010/06/30/wordnet-a-large-lexical-database-for-english/

### Day 002:
- https://karpathy.github.io/2019/04/25/recipe/
- https://karpathy.medium.com/yes-you-should-understand-backprop-e2f06eab496b

### Day 003:Tokenization and Encoding
- https://datajenius.com/2022/03/13/a-deep-dive-into-nlp-tokenization-encoding-word-embeddings-sentence-embeddings-word2vec-bert/

### Day 004:RNN
-https://www.youtube.com/watch?v=4KpRP-YUw6c&list=PLKnIA16_RmvYuZauWaPlRTC54KxSNLtNn&index=55
-https://karpathy.github.io/2015/05/21/rnn-effectiveness/
-https://colah.github.io/posts/2015-08-Understanding-LSTMs/


## LLM

### Day 01 : Fine-tune Llama-3.2-1B-Instruct-bnb-4bit  with Unsloth
- https://huggingface.co/blog/mlabonne/sft-llama3
- https://colab.research.google.com/drive/1T5-zKWM_5OD21QHwXHiV9ixTRR7k3iB9?usp=sharing#scrollTo=C_sGp5XlG6dq


### Day 02 : huggingface Transformer, Fine-tune LLM
-https://www.youtube.com/watch?v=jan07gloaRg&list=PLz-ep5RbHosU2hnz5ejezwaYpdMutMVB0&index=5
-https://www.youtube.com/watch?v=eC6Hd1hFvos&list=PLz-ep5RbHosU2hnz5ejezwaYpdMutMVB0&index=5
-https://www.datacamp.com/tutorial/unsloth-guide-optimize-and-speed-up-llm-fine-tuning
-https://docs.unsloth.ai/

### Day 03:
-https://www.youtube.com/watch?v=ZLbVdvOoTKM&list=PLz-ep5RbHosU2hnz5ejezwaYpdMutMVB0&index=11
- https://colah.github.io/posts/2015-09-NN-Types-FP/


## TOOLS:
-https://www.desmos.com/calculator


## Blog'S
- https://karpathy.ai/zero-to-hero.html
- https://colah.github.io/archive.html
- https://leetcode.com/explore/featured/card/machine-learning-101
- https://www.deep-ml.com/
- https://deepmleet.streamlit.app/
- https://github.com/karpathy/minGPT
- https://minigpt-4.github.io/
- https://distill.pub/
- https://lena-voita.github.io/nlp_course.html
  
## Tensorflow 
- https://datahacker.rs/tensorflow/
- https://machinelearningmastery.com/keras-functional-api-deep-learning/

## Day 01 : Introduction to TensorFlow 2.0
- https://datahacker.rs/introduction-into-tensorflow/

## Resources:
-https://github.com/greyhatguy007/Machine-Learning-Specialization-Coursera/tree/main
- https://github.com/greyhatguy007/deep-learning-specialization
- http://neuralnetworksanddeeplearning.com/
- https://datahacker.rs/neural-networks-with-python-and-pytorch/
- https://github.com/dvgodoy/PyTorchStepByStep
- https://madewithml.com/
- https://github.com/SylphAI-Inc/LLM-engineer-handbook
- https://www.marl-book.com/
- https://d2l.ai/index.html
- https://www.nlpdemystified.org/course
- https://github.com/codecrafters-io/build-your-own-x
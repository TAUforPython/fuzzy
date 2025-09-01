# FuzzyNet

[![DOI](https://zenodo.org/badge/265878050.svg)](https://zenodo.org/badge/latestdoi/265878050)

The model is separated into 7 different layers, these being:
1. Input layer
2. Membership Function Layer
3. Fuzzy Rule Layer
4. Input DR Layers
5. Fusion Layer
6. Fusion DR Layers
7. Task Driven Layer (Output Layer)

## 1. Brief Description

This is an implementation of a hierarchical fused deep neural network model proposed by Deng et al. (2007), used on the famous CIFAR-10 dataset for categorisation purposes.

## 2. Project Workflow
* Input layer starts with input vectors of an image of dimension (32x32x3), In this case there can be 32 vectors of size 32 for grey scale image and size 96 for coloured image.
* **Black** Each Input is connected with a membership function:
* Outputs of all membership functions are connected together using AND operation:
* **Blue** Now, all your Inputs are Densely connected by (blue) Input DR Layer using Sigmoid activation, by following formula:
    * There can be multiple Input DR Layers, we have used 2 layers as shown in the paper.
* **Green** Finally output of `Fuzzy Rule Layer` & `Input DR Layer` are fused together.
* Now, the fused output is passed through `Fusion DR Layer`. `Note: These can be multiple layers, we used single layer in this case`. Following formula is used to compute these layers. 
* **Red** The Final `Task Driven Layer` is the classification layer. That classifies using softmax function.
* After Classification loss is calculated using mean-square-loss `mse`.
    
## References

Deng, Y., Ren, Z., Kong, Y., Bao, F., & Dai, Q. (2017). A Hierarchical Fused Fuzzy Deep Neural Network for Data Classification. IEEE Transactions On Fuzzy Systems, 25(4), 1006-1012. doi: 10.1109/tfuzz.2016.2574915

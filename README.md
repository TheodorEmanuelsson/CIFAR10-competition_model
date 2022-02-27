# CIFAR10-competition_model
By: TheodorEmanuelsson and chayansraj

Model for the inclass competition in Neural Networks and Learnign System course at Linköping Univerity, spring 2022. The competition allows for only training for 50 epochs. Here we present our model when running for 50 epochs but also for XXX epochs. The model is build using tensorflow, keras and utilized a GPU via CUDA.

## The model

The model is inspired by GoogleNet but made some changes have been made to the architecture. We use regular convolutional blocks, inception blocks and downsampling blocks from GoogleNet but added to the depth and width of the original model. The model uses polynomial decay of the learning rate, Xavier initialization of weight and swish as activation function. The data is augmented by height and width shifts, vertical flips and filling by the nearest pixel.

![model](https://user-images.githubusercontent.com/49917684/155893219-6fbd5cb2-22c3-4259-8094-8846f33ce2ad.png)

## The results

**Trained for 50 epochs**


**Trained for XXX epochs**



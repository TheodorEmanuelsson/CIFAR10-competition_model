# CIFAR10-competition_model
By: TheodorEmanuelsson and chayansraj

Model for the inclass competition in Neural Networks and Learning Systems course at Linköping Univerity, spring 2022. The competition restricts training iterations to 50 epochs. The model is build using tensorflow, keras and utilized a RTX 2080 8GB GPU via CUDA.

## The model

The model is inspired by GoogleNet but some changes have been made to the architecture. We use regular convolutional blocks, inception blocks and downsampling blocks from GoogleNet but added to the depth and width of the original model. The model uses polynomial decay of the learning rate, Xavier initialization of weights and swish as activation function. The data is augmented by height and width shifts, vertical flips and filling by the nearest pixel.

The model starts with a convolutional module, followed by two inception modules. The output of the last inception module is used to disconnect the network into three paths, each using two inception modules each. The output from path1 and path2 are concatenated and followed by a convolutional modules in addition to a concatenation of path2 and path3 followed by a convolutional module. These two outputs are then concatenated into a narrow part of the network and followed by two convolutional blocks. After this, another split occurs to two paths which is run though three inception modules and one downsample module each. The results from these two paths are concatenated again and followed by two convolutional blocks. One last split occcurs for two paths with two inception modueles each before concatenation and average pooling is applied. After average pooling, a dropout layer with rate 0.5 is used to regularize the network before finally flattening, a dense layer with 10 hidden nodes and softmax activation.

![model](https://user-images.githubusercontent.com/49917684/155893219-6fbd5cb2-22c3-4259-8094-8846f33ce2ad.png)

## Results

**Trained for 50 epochs**

We achieved an accuracy of 91.21% on the test data when training for 50 epochs. The model has the most difficulty in distinguishing between cats and dogs.

![eval_50_white](https://user-images.githubusercontent.com/49917684/155899443-ec74dfac-e701-45eb-b5c1-8c0065f0f839.png)



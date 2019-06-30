# Neural Networks

Neural networks are not a new method. The first artificial neural network was devised in 1943, but advances in computational power and speed have made them a much more viable strategy for solving complex problems over the last 5-10 years. Originally devised by mathematicians and neuroscientists to illustrate the fundamental principles of how brains might work, they lost favor in the second half of the 20th century only to surge in popularity in the 20-teens as software engineers used them to resolve mathematically intractable problems. The application of neural networks to learning problems has been ongoing for 20 years, often to predict student behvior or to parse unstructured data such as student writing samples and provide natural sounding feedback through AI avatars.

## Goal for this project:

* To build a basic neural network to solve a prediction problem.
* To calculate teh accuracy of the neural network.

## Task for this project:

* To build a neural network to predict student attentional state from webcam images. The variables used to build a neural network model are the following:
  * eyes - student has their eyes open (1 = yes, 0 = no)
  * face.forward - student is facing the camera (1 = yes, 0 = no)
  * chin.up - student's chin is raised above 45 degrees (1 = yes, 0 = no)
  * attention - whether the student was paying attention when asked (1 = yes, 0 = no)

## Datasets:

* attention1.csv
* attention2.csv

## R packages:

* neuralnet
* caret

## Neural Network Models:

```
# One Hidden Layer
net <- neuralnet(attention ~ eyes + face.forward + chin.up, D1, hidden = 1, threshold = 0.01)
```
![Image of One Hidden Layer Model](https://github.com/lizarova777/neural-networks/blob/master/OneNeuralNet.png)

```
# Two Hidden Layers
net2 <- neuralnet(attention ~ eyes + face.forward + chin.up, D1, hidden = 2, threshold = 0.01)
```
![Image of Two Hidden Layers Model](https://github.com/lizarova777/neural-networks/blob/master/TwoNeuralNet.png)

## Results:

* The neural network with two hidden layers had a smaller final error rate than a neural network with one hidden layer. However, the overall accuracy for both models is 94%, with the true positive rate of 93.18% and true negative rate of 94.64%. In other words, both models sucessfully predicted whether the students were paying attention 94% of the time. 

## Intepretation:
* This model utilizes relevant facial movements recorded on the webcam in order to predict whether student was paying attention in the online discussion. These relevant facial movements are whether the student had their eyes open, whether the student is facing the camera, and whether the student's chin was raised above 45 degrees during the online discussion. Overall, the generated model is 94% accurate in successfully predicting whether the students are paying attention in the online discussion. 





# AI_FlappyBird
**Welcome to the tutorial!**

This tutorial involves making a simple game of flappy bird from scratch using Python and then using a neural network AI to master the game.

### 1.Programming the game
*We start coding the game using pygame library for python.*
  The co-ordinate axes is shown as below:![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/img_1.jpg)

The game creates a notion in which the bird appears to move right.
But in reality, the bird keeps on jumping in it's fixed x position  while the base and pipes keep moving towards the left.

*Also,the rapid shift between the bird images creates a notion that the bird is flapping it's wings*

![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/samples/bird1.png)   ![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/samples/bird2.png)   ![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/samples/bird3.png)
![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/samples/bird1.png)   ![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/samples/bird2.png)   ![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/samples/bird3.png)

***The stock values of the starting x position and velocity constants used seemed to me as best suited.
Feel free to mess with these values as long as the bird flaps xD***

### 2.Training the neural network using NEAT
NEAT Overview
NEAT (NeuroEvolution of Augmenting Topologies) is an evolutionary algorithm that creates artificial neural networks. For a detailed description of the algorithm, you should probably go read some of Stanley’s papers on his website.

Even if you just want to get the gist of the algorithm, reading at least a couple of the early NEAT papers is a good idea. Most of them are pretty short, and do a good job of explaining concepts (or at least pointing you to other references that will). The initial NEAT paper is only 6 pages long, and Section II should be enough if you just want a high-level overview.

In the current implementation of NEAT-Python, a population of individual genomes is maintained. Each genome contains two sets of genes that describe how to build an artificial neural network:

Node genes, each of which specifies a single neuron.
Connection genes, each of which specifies a single connection between neurons.

To evolve a solution to a problem, the user must provide a fitness function which computes a single real number indicating the quality of an individual genome: better ability to solve the problem means a higher score. The algorithm progresses through a user-specified number of generations, with each generation being produced by reproduction (either sexual or asexual) and mutation of the most fit individuals of the previous generation.


![Alt Text](https://miro.medium.com/max/1400/0*N4j_sl8M05G6pXZV.png)

*The activation function chosen is tanhx*

As we move towards infinity on the x-axis, the more closer the value is to 1.

Similarly as we move left from 0, the value moves towards -1.

![Alt Text](https://mathworld.wolfram.com/images/interactive/TanhReal.gif)

There are 2 types of incremental fitness values that we provide to a particular bird:

a. Existential Fitness-For each passing second,the fitness is incremented by 0.1*30=3

b. Monumental Fitness-For each toggled obstacle,the fitness increases by 5

The stock values of threshold,genomes etc are enlisted in the op.txt file.

**Feel free to change these values as and when required.**

Though,the model trained gives really exquisite results in the first/second generation itself.

![Alt Text](https://github.com/namantuli18/AI_FlappyBird/blob/master/img_2.jpg)

# MLPRegressor-Neural-Network-
This is a multi-layer perceptron neural network that is used to perform regression task on a housing datasets.

Neural Networks for Regression Tasks

Dataset: housing.csv

Report Document: Analysis Questions 
1. Explain, in your own words, the role of the “max_iter”, “learning_rate_init”, and “alpha” parameters. For each one, explain what effect it has on the learning process if the value of that parameter is increased versus decreased.

max_iter: This parameter represents the maximum number of iterations over the entire dataset. Increasing max_iter allows the model to learn more, improve accuracy and help the model converge if the model have not converged using the default number of iteration.  If max_iter is too big this can lead to overfitting because the model will be too closely trained, and it will not be able to generalize well. Decreasing the max_iter reduce the model ability to learn from the dataset and can lead to underfitting. Having a lower number of iterations can also cause a model to not converge if the number of iterations required is less. 
learning_rate_init: This parameter represents the initial learning rate; it controls the step size of the weights adjustments at each iteration. Increasing this parameter leads to larger steps taken and it can decrease the time it takes for the model to converge. On the other hand, decreasing the learning step result in smaller step taken and it increase the time it takes for the model to converge.  

alpha: This parameter represents the strength of the L2 regularization. Increasing alpha add more regularization and reduce the chances of the model to overfit by reducing the training score and increasing the test score. Decreasing alpha, reduce the strength of the model regularization and increase the chance of the model to overfit by increasing the training score.

2. Describe the process you used to identify neural network models of the various shapes that converged. What did you learn about configuring MLPRegression models from doing this work? 
My first step was to use the default setting to configure a simple model that have converged after 3000 number of iterations. After scaling the feature, I started experimenting with the parameters the alpha, the learning_rate_init and max_iteration. I increase the learning rate to 0.01 and the alpha to 0.001 for the model to quickly converge. My initial focus was to make the model converge. I started experimenting by increasing the max_iter from 3000 to 5000 and the model converged after 6000 number of iterations. 
Next, I added two hidden layers.  After experimenting with a larger first layer versus a smaller first layer, I noticed that my best training score and test score was achieved when I had in my hidden layers 90 units in my first layer and 105 in my second layer. Then I added a third layer and experimented by adding 10 units in the third layer. I noticed a drop in performance. My training score dropped from 82% to 81%, while my test score went down from 79% to 78%. I decreased the units in the third layer to 5 then to 4 and 6. My training score improved to 83% while maintaining a 79% test score. But reducing the third layer to 4 units or increasing it to 6 units lowered my model performance again. At this point my best training score was 83% and my test score was 79%.  I tried to see if by changing the max_iter, the alpha or the learning_rate_init I could improve the model further.
I created three arrays for each parameter respectively. 
max_iter=[3000, 5000, 8000, 10000]
alpha=[0.001, 0.01, 0.1, 1, 10]
learning_rate_init=[ 0.01, 0.1, 1, 10]
I used a for loop to loop through each value in the array while experimenting with only parameter at a time. Increasing or decreasing the value of the max_iter and the learning_rate_init didn’t make much difference but increasing alpha to 1 boosted my training score to 84% and my test score to 80%. 
From this homework I learned that configuring an MLP regressor models is an exploratory process. You have to experiment a lot, having more hidden layers increases the model learning ability. Increasing the learning rate reduces the time the model takes to converge. Also, I discovered that the right alpha value could further improve the model accuracy.  

3. Did you train any models that seem to be significantly underfitting the data? If so, give an example of where you saw underfitting, explaining what it is that you are observing that leads you to conclude this. If you do not observe any significant underfitting, explain why none of your trials represent underfitting.
No there was not a model that seemed to be significantly underfitting the data. The lowest performance was with the simple model with max_iter of 3000. The training and test accuracies are 69% and 68% respectively. Although those test scores are not high, they are not extremely low considering the dataset that we are using. The other models test, and training score range from 70% to 84%. This shows that the model can learn and understand the pattern from the dataset. 

4. Did you train any models that seem to be significantly overfitting the data? If so, give an example of where you saw overfitting, explaining what it is that you are observing that leads you to conclude this. If you do not observe any significant overfitting, explain why none of your trials represent overfitting.

No there was no overfitting in my models. The gap between my training scores and my test scores for each is minimal. Also, I’m using regularization of 0.001 to prevent my model to overfit.

5. Describe the end model you settled on as the best model. What is the shape of the network – how many hidden layers does it have, with how many hidden units per layer? What other parameter settings were required to achieve this best performance?

The final shape of my model has a max_iter at 6000, an alpha of 1, a learning_rate_init of 0.01, and three hidden layers with 90 units in the first layer, 105 units in the second layer and 5 units in the third layer with a random_state of 42.

6. Overall, what conclusions were you able to draw about what shapes or configurations are best suited for a model of this problem? For example, are bigger or smaller layers of units better? Are more or fewer layers better? What in your data leads you to these conclusions?

I think that a configuration with bigger units performs better for this dataset, also adding a third layer with 5 units improved the performance of the model. But thinking back about having more than 5 units or less, I can conclude that there is a specific unit in the third layer that can potentially improve the model accuracy further. To sum up, having three hidden layers and big units in the first- and second-layer work well for this type of problem. The third layer units need to be figured out to improve the model accuracy. 

7. Looking back at your results from Coding Assignment Three, compare the performance of your multilayer perceptron network to the performance of the best linear model you trained from that assignment, including a reminder of your best scores for a linear model on this data. Does this problem seem better suited for learning with a linear model or a neural network? Why?
The multilayer perceptron neural network is better suited for learning. My best score from the Linear model is 72% for the training score accuracy and 68% for the test score accuracy, while my multilayer perceptron neural network best score are 84% for a training score and 80% for a test score.  

8. What have you learned in general about training neural networks through this process
I learned that training neural networks is an exploratory process. Understanding the model parameters are keys to having some insight on how to improve the model accuracy and find the right configuration or shape of the model. 

 





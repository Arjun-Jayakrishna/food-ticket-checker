# food-ticket-checker

Introduction

My approach to this project was to create a machine learning model that would be able to consistently distinguish between the real and counterfeit food tickets from the University of Toronto in the pursuit of equality among the students.

Data

For every food type (hamburger, hotdog, and ramen), I made a single counterfeit ticket, which I then put against 3 different backgrounds, just like the real tickets. Thus, when I finished, I had 9 real images and 9 counterfeit images going into the process of data augmentation. 

Solution Design Process

There are three primary approaches that I could take when designing my solution to the posed problem. 

The first approach would be to use a Convolutional Neural Network (CNN) model. This network type is specifically meant for the task of image classification. As such, for our purposes in this project, a CNN model would likely be very efficient and accurate. However, a downside of CNN models is that they can be more difficult to fully understand; it can also take longer to determine the best hyperparameters for these models.

The second approach would be to use an Artificial Neural Network (ANN) model. This network type is known for its proficiency in solving complex computational problems. Although it can be used for image classification tasks as well, it is definitely not its main focus. As such, an ANN model would likely be much less accurate and take longer to train than a CNN model. The upside of ANN models, however, is that they are much easier to understand. 

The third and final approach that could be used was transfer learning. This would involve finding a machine learning model that has already been trained for a general task (in this case it would be classifying images), and then applying it to a similar task that is more specific (for us it would be identifying different types of tickets). The primary benefit of this approach would be that I wouldn’t need to spend time developing a model; I’d just need to work on adjusting the hyperparameters. However, a con of this would be that less customization is available; it might also take time to find an existing model that actually works.

In the end, after considering the pros and cons of all 3 of these approaches, I chose to go with the ANN model approach. In addition to being easier to understand (generally), ANN models are widely known to perform relatively well even when there is incomplete input (though this problem probably won’t be faced by us).

Final Architecture

Here are some of the hyperparameters that I considered when working on the model:

Batch Size: I eventually settled on a value of 32 for this hyperparameter. I read that it is best practice for it to be a power of 2.
Number of Epochs: I just chose random values for this hyperparameter until I got the best results that I could.
Momentum: I just kept this value as 0.9, which is the standard.

Also note that I used CrossEntropyLoss for my loss criteria.

Results

The final training accuracy of my model was about 50.5%. On the other hand, the final validation accuracy of the model was about 49.7%. 

Discussion

Based on the data compiled in the previous section, I can conclude that my model isn’t performing very well. Specifically, the final training accuracy being 50.5% means that for the images that the model was trained on, there is about a 1 in 2 chance that it is correct. On the other hand, the final validation accuracy being 49.7% means that for images that the model is unfamiliar with, there is also about a 1 in 2 chance of it being correct. This latter stat is actually worse since it is below 50%, meaning it’s more likely to output an incorrect answer than a correct one.

I think the main reason why my model performed poorly was that I didn’t experiment with the hyperparameters very much; I only made extremely basic changes to them. I believe that if I had tried more combinations of these hyperparameters, I could have ended up with a much more successful model. Case in point, my first attempt at creating the ANN model yielded accuracy percentages of around 10% each. Nevertheless, just a little bit of tweaking led to both percentages shooting up to around 50%. However, I also understand that at a certain point, peak accuracy percentages will be reached and modifying the hyperparameters won’t really do much.

Additionally, it should be noted that as mentioned before, ANN models, for the task of image classification, are expected to perform much worse than CNN models since the latter are made specifically for this task.

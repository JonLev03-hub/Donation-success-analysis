# Donation-success-analysis
Large companies have millions of dollars that they are willing to donate to charity but its always a hard decision to pick the right one that will use the money most effectively. I will be using deep learning models to predict the best way to allocate that money.

To achieve this I will be reviewing a list of previous applicants inside a neural network. This dataframe is displayed below. 
![image](https://user-images.githubusercontent.com/81537476/155869757-05aa5307-63b8-4064-9ed0-2a20fff8427a.png)

This data had already been relatively clean, so to prep this data I simply had to use the OneHotEncoder on the categorical data. 

The target was the status column. 

For the first attempt I created a neural network using Relu as the activation function for two hidden layers (node count of 5 and 7), and a sigmoid function as the output. This resulted with a accuracy of approximately 56% after 50 epochs. As this is obviously not effective for a solution I setup a quick boute force method that could try a large sum of combimations. after testing 485 combinations I was able to get some interesting results, then I did another batch test and canceled it after 65 rounds due to poor results. 

This first batch of tests was allowing either 4,6 or 8 nodes per hidden layer and testing all combinations of relu, sigmoid, and tanh functions. after 485 attempts with 50 epochs each the best result I found was 71% success. 

This was found with 8 nodes in hidden layer one and 4 in the second hidden layer. Both hidden layers were using relu as the activation functions and sigmoid as the output activation function.

the second batch of tests restricted the output function to sigmoid, and allowed many more nodes, ranging from 10-40 with steps of 4; this batch also ran 100 epochs each. after 65 iterations I ended this test because the results seemed very similar to the first test with half or less nodes. 

Compiling data from both test it seems that using relu as an activation function returns an average 5% higher performance in this dataset, but to get performance to 75% or more I need to make more adjustments.

the data for most the test is saved in csv files inside the github. , along with the top performing model saved as an h5 file. 

To further the testing I had created another test allowing the hidden nodes to contain 12, 24 or 36 nodes, and using relu for both hidden functions, and sigmoid for the output functions since that produced the best results. This test repeated all combinations 10 times and saved the average, and with the results I made a few graphs. 

![image](https://user-images.githubusercontent.com/81537476/155891842-08607e26-5359-419f-afbe-7dec108cb90d.png)
![image](https://user-images.githubusercontent.com/81537476/155891850-b3e75259-5ac4-48d9-9002-845fc08d9d8a.png)

Above I have listed the average performance by number of hidden layer one or hidden layer two nodes. With this test I still returned an average of 59% accuracy with a maximum of 71%. so verry similar to the other tests. 



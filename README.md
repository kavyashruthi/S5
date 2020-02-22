Step -1: Batch Normalization
---------------------------------------------------------------
Target:
1.	Get the set-up right, Set Transforms, Set Data Loader, Set Basic Working Code, Set Basic Training  & Test Loop
2.	Add Batch-norm to increase model efficiency.
Results:
1.	Parameters: 10.9k
2.	Epoch range : 15
3.	Best Train Accuracy: 99.81
4.	Best Test Accuracy: 99.21 
Analysis:
1.	We see over-fitting here
2.	Even if the model is pushed further, it won't be able to get to 99.4


Step - 2 Regularization
---------------------------------------------------------------
Target:
1.	Add Regularization, Dropout (add dropout=0.25 after 3rd and 6th conv layer) 
Results:
1.	Parameters: 10.9k
2.	Epoch range: 15
3.	Best Train Accuracy: 99.31
4.	Best Train Accuracy: 99.20
Analysis:
1.	Regularization working. 
2.	But with current capacity, not possible to push it further. 

Step 3: Global Average Pooling
---------------------------------------------------------------
Target:
1.	Add GAP and remove the last BIG kernel. 
Results:
1.	Parameters: 6k
2.	Epoch range: 15
3.	Best Train Accuracy: 98.58
4.	Best Test Accuracy: 98.27 
Analysis:
1.	We are comparing a 10.9k model with 6k model. Since we have reduced model capacity, reduction in performance is expected. 

Step 4: VOILA
---------------------------------------------------------------
Target:
1.	Increase model capacity at the end (add layer after GAP)
2.	Perform MaxPooling
3.	Fix DropOut, add it to each layer 
Results:
1.	Parameters: 7.8k
2.	Epoch range: 15
3.	Best Train Accuracy: 98.70
4.	Best Test Accuracy: 99.30   
Analysis: 
1.	Works!
2.	The model is not over-fitting at all. 

Step 5 : Image Augmentation
---------------------------------------------------------------

Target: 
1. Add rotation, our guess is that 5-7 degrees should be sufficient.  
Results:
1.Parameters: 7.8k
2. Epoch range: 15 
3. Best Train Accuracy: 98.99
4. Best Test Accuracy: 99.40 (13th Epoch) 
Analysis:
The model is under-fitting now. This is fine, as we know we have made our train data harder. 
The test accuracy is also up, which means our test data had few images which had transformation difference w.r.t. train dataset

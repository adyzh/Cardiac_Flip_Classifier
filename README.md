# Cardiac_and_Full-Lung_CT_Classifier

A General Algorithm for Cardiac CT Flip Detection using Quadrant Pixel Summation
For cardiac scans, there exists no clean up directory: Manually check for 160 scans for trainning. Goal: creat a function such that given mask, the function outputs axes to flip on if mask indicates potential flipping.

Data Preparation

For each subject, we have three lung masks, one for each view (axial, coronal and saggital).
Manually generate Left-Right (LR), Top-Bottom (TB) and Front-Back (FB) flips and store Niftys in specified subdirectories.
Method

Randomly sample 200 subjects from MESA Ex1, clean up then conduct manual flip generation per step (2) in data preparation.
Extract the lung mask per subject, divide each mask into four quadrants and sum up the pixels in each quadrant, thereby creating a 3x2x2 tensor for each subject.
Train a support vector classifier on 4 classes x 200 scan per class = 800 scans; save the classifier and call for future function.

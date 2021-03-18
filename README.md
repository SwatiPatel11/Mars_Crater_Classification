# Mars_Crater_Classification

This dataset was generated using HRSC nadir panchromatic image h0905_0000 taken by the Mars Express spacecraft. The images are located in the Xanthe Terra, centered on Nanedi Vallis and covers mostly Noachian terrain on Mars. The image had a resolution of 12.5 meters/pixel.

Problem statement
Determine if the instance is a crater or not a crater. 1=Crater, 0=Not Crater

About the dataset
Using the technique described by L. Bandeira (Bandeira, Ding, Stepinski. 2010.Automatic Detection of Sub-km Craters Using Shape and Texture Information) we identify crater candidates in the image using the pipeline depicted in the figure below. Each crater candidate image block is normalized to a standard scale of 48 pixels. Each of the nine kinds of image masks probes the normalized image block in four different scales of 12 pixels, 24 pixels, 36 pixels, and 48 pixels, with a step of a third of the mask size (meaning 2/3 overlap). We totally extract 1,090 Haar-like attributes using nine types of masks as the attribute vectors to represent each crater candidate. The dataset was converted to the Weka ARFF format by Joseph Paul Cohen in 2012.

pipeline

Attribute Information:
We construct an attribute vector for each crater candidate using Haar-like attributes described by Papageorgiou 1998. These attributes are simple texture attributes that are calculated using Haar-like image masks that were used by Viola in 2004 for face detection consisting of only black and white sectors. The value of an attribute is the difference between the sum of gray pixel values located within the black sector and the white sector of an image mask. The figure below shows nine image masks used in our case study. The first five masks focus on capturing diagonal texture gradient changes while the remaining four masks on horizontal or vertical textures.

How to read an image?
Python supports very powerful tools when comes to image processing. Matplotlib is an amazing visualization library in Python for 2D plots of arrays. Matplotlib is a multi-platform data visualization library built on NumPy arrays and designed to work with the broader SciPy stack. It was introduced by John Hunter in the year 2002. We will use the Matplotlib library to convert the image to numpy as an array.

We import image from the Matplotlib library as mpimg.
Use mpimg.imread to read the image as numpy as array.
** INPUT **

import matplotlib.image as mpimg
<div class="w-percent-100 flex-hbox flex-cross-center flex-main-center">
          <div style="width:100%" class="flex-auto">
            <div style="width:100%; max-width:100%; overflow: hidden "><p><img src="https://storage.googleapis.com/ga-commit-live-prod-live-data/account/b92/11111111-1111-1111-1111-000000000000/b-43/9301164e-92b3-4f64-b699-737433839cd8/file.png" alt="tile" /></p></div>
          </div>
        </div>

image = mpimg.imread('crater1.png')
** OUTPUT **

array([[0.40784314, 0.40784314, 0.40784314, ..., 0.42745098, 0.42745098,
        0.42745098],
       [0.4117647 , 0.4117647 , 0.4117647 , ..., 0.42745098, 0.42745098,
        0.42745098],
       [0.41960785, 0.41568628, 0.41568628, ..., 0.43137255, 0.43137255,
        0.43137255],
       ...,
       [0.4392157 , 0.43529412, 0.43137255, ..., 0.45490196, 0.4509804 ,
        0.4509804 ],
       [0.44313726, 0.44313726, 0.4392157 , ..., 0.4509804 , 0.44705883,
        0.44705883],
       [0.44313726, 0.4509804 , 0.4509804 , ..., 0.44705883, 0.44705883,
        0.44313726]], dtype=float32)
NOTE: The images of the crater has already been converted to numpy array and is provided.

A zipped file containing the following items is given:

train.csv
The data file train.csv contains the 5892 instances with the 1091 features including the target feature.

test.csv
The datafile test.csv contains the 1473instances with the 1090 features excluding the target feature.

sample_submission.csv
Explained under the Submission sub-heading

Mars_Crater_Data_Dictionary.csv
The file contains data dictionary(Dictionary explaining what each feature of the dataset means) of the Insurance Claim dataset

Mars_Crater_Student_Template.ipynb
A template notebook explaining the task breakdown to solve the given problem statement (Learners are recommended to use it)

Submission
After training the model on train.csv data, the learner has to predict the target feature of the test.csv data using the trained model. The learner has to then submit a CSV file with the predicted feature.

Sample submission file(sample_submission.csv) is given to you as a reference to the format expected when you submit

Evaluation metrics
For this particular dataset, we are using roc_auc_score as the evaluation metric.

Submissions will be evaluated based on ROC-AUC Score as per the below threshold.

Your roc_auc_score score	Points earned for the Task
0.89 <= roc_auc_score	100% of the available points
0.87 <= roc_auc_score < 0.89	80% of the available points
0.84 < roc_auc_score < 0.87	70% of the available points
roc_auc_score <= 0.84	No points earned
Why solve this project?
After completing this project, you will have a better understanding of how to optimize a machine learning model. In this project, you will apply the following concepts.

Train-test split
Machine Learning Algorithms
Ensemble Techniques
Evaluation Metric ROC-AUC Score
Skills Covered:
Decision Trees
Ensemble Methods

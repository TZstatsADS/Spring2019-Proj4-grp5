# Project: OCR (Optical Character Recognition) 

![image](figs/Tesseract_OCR_logo_(Google).png)

Attention!!!!!!! Our detection file is in the doc and our correction file is in main menu.!!!!!!!!!!!!!!




### [Full Project Description](doc/project4_desc.md)
Our team is trying to realize the algorithm from paper D3 + C4. 
For the detection part, we firstly constructed features that we can use to define a "garbadge" word. For instance: 

(1) When we delete both the first and the last symbol of a string and the rest contains at least two distinct punctuation symbols, then the string is garbage.

(2) If a string starts and ends with lower-case letters and contains an upper-case letter it is garbage.

(3) A string composed of more than 20 symbols is garbage. 

(4) A string containing at least 3 consecutive occurrences of the same symbol is garbage.

(5) If the number of upper-case letters is larger than the number of lower-case letters and the string contains both types of letters it is garbage.

(6) If a string is only composed of vowels and consonants and the the number of consonants is greater than 8 times the number of vocals, or vice versa, the string is garbage.

(7) If a string contains 4 consecutive vowels or 5 consecu- tive consonants it is garbage.

We extract these features from our training text data and applied the rules mentioned in the following of the paper to assign values to theses features. Finally, we construct the dataframe of these features and use SVM to train our model. 
Our result is quite pleasant: 

![image](figs/de.jpeg)


For the correction part, we realize the paper C4. We mainly use 3 different ways to calculate the probability of the potential correct words. 

![image](figs/cor.jpg)




Term: Spring 2019

+ Team 3
+ Shaofu Wang : 1) according to correction paper4 write prior probability python code for three methods, mle, ele and gt. 2) design get_candidate function for four methods deletion, insertion, substitution and revesal of typo. 3) debug for correction part.


+ Yiwei Li: 1) according to detection paper write error detection python code , including feature generation, specifically, the feature is generated based on the rules which can judge garbage. 2) Apply SVC model on the train data to construct Classifier model and test the model. 3) Construct performance measurement to get word precision and recall of three different correction methods, and character precision and recall of three different correction methods


+Shengwei Huang: 1) Write the function to extract the correpsonding features in the detection part. 2) Construct the features and apply the garbadge words rules to the detection part. Then, apply the SVM model to train our training dataset and test dataset. Finally, to use our model to predict the test dataset and read our output into excel.  3) Work on the correction part specifically in GT part to handle with empty set probelms, left/right words probability and summarize the all results. 
			
			
+ Liwei Zhang: 1) By understanding the correction paper, wrote the p(l|c)/p(r|c) function as a part that's used to compute the final result. 2) Worked on the final function, especially for p(c) and p(tr) parts, by handling out of index problems and storing results.


+ Xishi Chen: 1) wrote part of functions for features extraction in detection part 2) apply SVM model to data in detection part 3) wrote char matrix and conditional probability p(t|c) in correction. 4) debug for correction part, like deal with out of index problem and meaningless return in candidate choosing


+ Project summary: In this project, we created an OCR post-processing procedure to enhance Tesseract OCR output. 
	


Following [suggestions](http://nicercode.github.io/blog/2013-04-05-projects/) by [RICH FITZJOHN](http://nicercode.github.io/about/#Team) (@richfitz). This folder is orgarnized as follows.

```
proj/
├── lib/
├── data/
├── doc/
├── figs/
└── output/
```

Please see each subfolder for a README file.



**Decoding fMRI with Different Classifiers**
----------------------------------------

1. Overview
-----------
[Scikit-learn](http://scikit-learn.org/stable/), a standard machine learning libary, provides handy tools for fMRI analysis. [Nilearn](http://nilearn.github.io/index.html), a machine learning library seeks to simplify the use of Scikit-learn for neuroimaging. It provides an easier way to load, preprocess, mask, and visualize neuroimaging data.

A public dataset from [Haxby et al](http://dev.pymvpa.org/datadb/haxby2001.html#download) was used for analysis. It consists of 6 subjects with 12 fMRI sessions for each. These subjects were prescribed 6 different visual stimuli (i.e. faces, houses. chairs, scissors, shoes, and bottles) which can excite different cortical regions in the brain. 

Three different classifiers (**support vector machine, logistic regression, Ridge classier**) with and without cross-validation were compared in terms of F1 scores (F1 = 2* precition * recall / (precition + recall) ) for classifying the stimuli categories. 

2. Background
-----------
Machine learning plays an increasing role in neuroimaging, specifically in functional magnetic resonance imaging (fMRI). fMRI is a functional neuroimaging technique using MRI techniques to measure brain activity by detecting changes associated with blood flow ([fMRI in Wikipedia](https://en.wikipedia.org/wiki/Functional_magnetic_resonance_imaging)).

- ***Supervised learning:***  supervised learning is very useful to encode and decode brain MRI images associated with external stimuli or clinical presentations. External stimuli, such as vision, smell, taste, sound, can excite specific types of neurons which make corresponding brain cortex more active. fMRI can be used to measure the level of brain activities by comparing the signals between the resting state and excited state.

- ***Unsupervised learning:*** unsupervised learning is also very important to unveil some unknown brain networks and functions based on the resting-state fMRI. Clustering is of particular interests to discover the connectivity of brain functionality. 

3. Results
-----------
The first subject (subject_number = 0) and four of the stimuli (bottle, cat, face, house) were chosen for analysis. 

***3.1 Classifer-Specific Accuracy***
To compare the discriminative scores (F1-scores) grouped by classifers.
![alt tag](https://cloud.githubusercontent.com/assets/17630430/14061046/12d385f2-f344-11e5-88c0-b814fb96643e.png "classifier f1 scores")

***3.2 Stimulus-Specific Accuracy***
To compare the discriminative scores (f1-scores) grouped by stimuli.
![alt tag](https://cloud.githubusercontent.com/assets/17630430/14060942/6d208db4-f341-11e5-9757-d7070bd5df84.png "stimulus f1 scores")

***3.3 Mapping on MRI Images***
To compare the classifer weightes mapped onto EPI (echo planar imaging) MRI iamges.
![alt tag](https://cloud.githubusercontent.com/assets/17630430/14061006/07a9883a-f343-11e5-9458-f08e58433c89.png "EPI_Classifers")

From the results, we can see that bottles and houses can be more easily discriminated by classifiers compared to cat and face. The difference between the four classifiers was not very significant, but SVC provides slightly better accuracy for classifying the house and face.

4. To Do
-----------
***4.1 Parameter Optimization***
Although cross validation with GridSearchCV was performed for a couple of different C values, a more dense search should be performed to optimize the classifier parameters.

***4.2 More Data Test***
The test was only performed on a single subjects. The original dataset includes 6 subjects, thus it is interesting to look into the classification difference between subjects.

5. References
-----------
[1] http://scikit-learn.org/stable/
[2] http://nilearn.github.io/
[3] Haxby JV, et al. Distributed and overlapping representations of faces and objects in ventral temporal cortex. Science 2011; 293:2425-2430.
[4] Abraham A, et al. Machine learning for neuroimaging with scikit-learn. Front Neuroinfor 2014; 8:14.
[5] http://nilearn.github.io/auto_examples
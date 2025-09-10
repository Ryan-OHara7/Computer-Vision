"In 2013, we hosted one of our favorite for-fun competitions:  Dogs vs. Cats. Much has since changed in the machine learning landscape, particularly in deep learning and image analysis. Back then, a tensor flow was the diffusion of the creamer in a bored mathematician's cup of coffee. Now, even the cucumber farmers are neural netting their way to a bounty.

Much has changed at Kaggle as well. Our online coding environment Kernels didn't exist in 2013, and so it was that we approached sharing by scratching primitive glpyhs on cave walls with sticks and sharp objects. No more. Now, Kernels have taken over as the way to share code on Kaggle. IPython is out and Jupyter Notebook is in. We even have TensorFlow. What more could a data scientist ask for? But seriously, what more? Pull requests welcome.

We are excited to bring back the infamous Dogs vs. Cats classification problem as a playground competition with kernels enabled. Although modern techniques may make light of this once-difficult problem, it is through practice of new techniques on old datasets that we will make light of machine learning's future challenges.

Evaluation
Submissions are scored on the log loss:
where

n is the number of images in the test set
\\( \hat{y}_i \\) is the predicted probability of the image being a dog
\\( y_i \\) is 1 if the image is a dog, 0 if cat
\\( log() \\) is the natural (base e) logarithm
A smaller log loss is better." - Kaggle 

The link to the competition can be found here: https://www.kaggle.com/competitions/dogs-vs-cats-redux-kernels-edition

The link to the dataset can be found here: https://www.kaggle.com/competitions/dogs-vs-cats-redux-kernels-edition/data

***** This model achived a log loss score of 0.75*********

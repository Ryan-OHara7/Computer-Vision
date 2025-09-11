"We recognize the works of artists through their unique style, such as color choices or brush strokes. The “je ne sais quoi” of artists like Claude Monet can now be imitated with algorithms thanks to generative adversarial networks (GANs). In this getting started competition, you will bring that style to your photos or recreate the style from scratch!

Computer vision has advanced tremendously in recent years and GANs are now capable of mimicking objects in a very convincing way. But creating museum-worthy masterpieces is thought of to be, well, more art than science. So can (data) science, in the form of GANs, trick classifiers into believing you’ve created a true Monet? That’s the challenge you’ll take on!

The Challenge:
A GAN consists of at least two neural networks: a generator model and a discriminator model. The generator is a neural network that creates the images. For our competition, you should generate images in the style of Monet. This generator is trained using a discriminator.

The two models will work against each other, with the generator trying to trick the discriminator, and the discriminator trying to accurately classify the real vs. generated images.

Your task is to build a GAN that generates 7,000 to 10,000 Monet-style images.

Getting Started:
Details on the dataset can be found here and an overview of the evaluation process can be found here.

To learn how to submit and answers to other FAQs, review the Frequently Asked Questions.

Recommended Tutorial
We highly recommend Amy Jang's notebook that goes over the basics of loading data from TFRecords, using TPUs, and building a CycleGAN.
Although the competition dataset only includes Monet images, check out this dataset for Cezanne, Ukiyo-e, and Van Gogh paintings to run your GAN on.

Evaluation
MiFID
Submissions are evaluated on MiFID (Memorization-informed Fréchet Inception Distance), which is a modification from Fréchet Inception Distance (FID).

The smaller MiFID is, the better your generated images are.

What is FID?
Originally published here (github), FID, along with Inception Score (IS), are both commonly used in recent publications as the standard for evaluation methods of GANs.

In FID, we use the Inception network to extract features from an intermediate layer. Then we model the data distribution for these features using a multivariate Gaussian distribution with mean µ and covariance Σ. The FID between the real images 
 and generated images" - Kaggle 

 The link to the competition can be found here: https://www.kaggle.com/competitions/gan-getting-started/overview
 The link to the dataset can be found here: https://www.kaggle.com/competitions/gan-getting-started/data

 The results were not perfect, but it was a great intro into GANs, what they can do, and how powerful they can be. 

Finally, this memorization term is applied to the FID:


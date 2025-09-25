Self-driving technology presents a rare opportunity to improve the quality of life in many of our communities. Avoidable collisions, single-occupant commuters, and vehicle emissions are choking cities, while infrastructure strains under rapid urban growth. Autonomous vehicles are expected to redefine transportation and unlock a myriad of societal, environmental, and economic benefits. You can apply your data analysis skills in this competition to advance the state of self-driving technology.

Lyft, whose mission is to improve people’s lives with the world’s best transportation, is investing in the future of self-driving vehicles. Level 5, their self-driving division, is working on a fleet of autonomous vehicles, and currently has a team of 450+ across Palo Alto, London, and Munich working to build a leading self-driving system (they’re hiring!). Their goal is to democratize access to self-driving technology for hundreds of millions of Lyft passengers.

From a technical standpoint, however, the bar to unlock technical research and development on higher-level autonomy functions like perception, prediction, and planning is extremely high. This implies technical R&D on self-driving cars has traditionally been inaccessible to the broader research community.

This dataset aims to democratize access to such data, and foster innovation in higher-level autonomy functions for everyone, everywhere. By conducting a competition, we hope to encourage the research community to focus on hard problems in this space—namely, 3D object detection over semantic maps.

In this competition, you will build and optimize algorithms based on a large-scale dataset. This dataset features the raw sensor camera inputs as perceived by a fleet of multiple, high-end, autonomous vehicles in a restricted geographic area.

If successful, you’ll make a significant contribution towards stimulating further development in autonomous vehicles and empowering communities around the world.

Evaluation This competition is evaluated on the mean average precision at different intersection over union (IoU) thresholds. The IoU of a set of predicted 3D bounding volumes and ground truth bounding volumes is calculated as:

The metric sweeps over a range of IoU thresholds, at each point calculating an average precision value. The threshold values range from 0.5 to 0.95 with a step size of 0.05: (0.5, 0.55, 0.6, 0.65, 0.7, 0.75, 0.8, 0.85, 0.9, 0.95). In other words, at a threshold of 0.5, a predicted object is considered a "hit" if its intersection over union with a ground truth object is greater than 0.5.

At each threshold value , a precision value is calculated based on the number of true positives (TP), false negatives (FN), and false positives (FP) resulting from comparing the predicted object to all ground truth objects:

A true positive is counted when a single predicted object matches a ground truth object with an IoU above the threshold. A false positive indicates a predicted object had no associated ground truth object. A false negative indicates a ground truth object had no associated predicted object.

Important note: if there are no ground truth objects at all for a given image, ANY number of predictions (false positives) will result in the image receiving a score of zero, and being included in the mean average precision.

The average precision of a single image is calculated as the mean of the above precision values at each IoU threshold:

In your submission, you are also asked to provide a confidence level for each bounding box. Bounding boxes will be evaluated in order of their confidence levels in the above process. This means that bounding boxes with higher confidence will be checked first for matches against solutions, which determines what boxes are considered true and false positives.

NOTE: In nearly all cases confidence will have no impact on scoring. It exists primarily to allow for submission boxes to be evaluated in a particular order to resolve extreme edge cases. None of these edge cases are known to exist in the data set. If you do not wish to use or calculate confidence you can use a placeholder value - like 1.0 - to indicate that no particular order applies to the evaluation of your submission boxes. The two boxes in the visualization overlap, but the area of the overlap is insubstantial compared with the area taken up by both objects together. IoU would be low - and would likely not count as a "hit" at higher IoU thresholds.

The difference between the 2D and 3D bounding volume contexts is small. In the 3D context we reduce the bounding volume to a ground bounding box and a height. The IoU is then the intersection of the ground bounding boxes * the intersection of the height differences, divided by the union of the bounding boxes.

Submission File The submission format requires a space delimited set of bounding volume parameters. For example:

97ce3ab08ccbc0baae0267cbf8d4da947e1f11ae1dbcb80c3f4408784cd9170c,1.0 2742.15 673.16 -18.65 1.834 4.609 1.648 2.619 car

indicates that sample 97ce3ab08ccbc0baae0267cbf8d4da947e1f11ae1dbcb80c3f4408784cd9170c has a bounding volume with a confidence of 0.5, center_x of 2742.15, center_y of 673.16, center_z of -18.65, width of 1.834, length of 4.609, height of 1.648, yaw of 2.619, and a class_name of car.

The file should contain a header and have the following format. Each row in your submission should contain ALL bounding boxes for a given image.

Lastly, the score returned by the competition metric is the mean taken over the individual average precisions of each image in the test dataset.

***KAGGLE PAGE CAN BE FOUND HERE: https://www.kaggle.com/competitions/3d-object-detection-for-autonomous-vehicles/ ***DATASETS CAN BE FOUND HERE: https://www.kaggle.com/competitions/3d-object-detection-for-autonomous-vehicles/data

Intersection over Union (IoU) Intersection over Union is a measure of the magnitude of overlap between two bounding boxes (or, in the more general case, two objects). It calculates the size of the overlap between two objects, divided by the total area of the two objects combined.

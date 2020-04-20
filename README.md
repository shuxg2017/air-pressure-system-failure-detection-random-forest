# Tree Methods For Air Pressure System Failure Detection At Scania Trucks

In this project, we use basic decision tree and random forest for binary classification task. The observations in the dataset are either negative or positive. Positive cases are more significant than negative cases. One false negative (positive case classified as negative) will lose 500 bucks, but one false positive (negative case classified as positive) will lose 10 bucks. **Our goal is to minimize the cost.**

### Our best testing dataset result by using random forest
![best result](https://github.com/shuxg2017/Air-pressure-system-failure-detection-by-tree-forest/blob/master/random_forest_confusion_matrix.png)


## Introduction

- **Our result overview**
  - Best tree costs: original training dataset ($34190), original testing dataset ($11910)
  - Best forest costs: original training dataset ($23300), original testing dataset ($10150)
  - Our best result beats the second place in Industrial Challenge 2016 at the 15th International Symposium on Intelligent Data Analysis
- **Ranks in the Industrial Challenge 2016 (Testing cost/False positive/False negative)**
  - rank 1: 9920/542/9
  - rank 2: 10900/490/12
  - rank 3: 11480/398/15
  - unranked: 10150/615/8 **(our random forest model)**
- **Dataset split**
  - Original training dataset split to training (85%: 51k observations) and validation (15%: 9k).
  - Original testing dataset is given (16k).
- **Technique to find the best tree/forest**
  - Smote for minority class, the positive cases
  - Random search (give general idea of the best possible hyperparameter settings)
  - Grid search (increase the search resolution based on random search)
- **Technique to tune the best tree/forest**
  - Apply probabilities in leaves
  - Do threshold optimization on validation dataset (find best threshold)
- **Prediction**
  - Given the best tree/forest, apply the optimal threshold on testing dataset
  - **Note: the optimal threshold is found by using the validation dataset.**

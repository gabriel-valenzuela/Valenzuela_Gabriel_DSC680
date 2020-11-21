# Kickstarter Video Game Success

## Applied Data Science Project 

![Kickstarter Name](https://github.com/gabriel-valenzuela/gabriel-valenzuela.github.io/blob/master/images/kickstarterFullName.png)

### Objective

When it comes to the area that I am looking into for this proposal, I will be studying the world of crowdfunding for indie or smaller video games not produced by larger publishers. However, more specifically, I will be looking into Kickstarter as a whole and what factors a small team of video game developers can leverage to raise funds to publish the game on their own accords. 

With the following data set, I am proposing that it be analyzed to determine what factors lead to a successful Kickstarter project, as well as the factors that lead to a video game Kickstarter reaching its funding goal. At the same time, to investigate the overall success rate of releasing a project. The formal research questions are as follows:

What factors lead to a successful, reaching the set funding goal, Kickstarter project on the platform?

What factors lead to a successful, reaching the set funding goal, video game Kickstarter project on the platform?

What is the success rate, reaching the set funding goal, of releasing a video game overall?


### Data Source

https://www.kaggle.com/kemical/kickstarter-projects

### Methodology

Random Forest Classifier (Preview of Model)

To see entire code for analysis, look into project folder.

```python

#creating test and train dependent and independent variables
train_ind, test_ind, train_dep, test_dep = train_test_split(kick_projects_ip_scaled_ftrs, kick_projects_ip[response], test_size=0.3, random_state=0)

features_count = train_ind.shape[1]

parameters_rf = {'n_estimators':[50], 'max_depth':[20], 'max_features': 
                     [math.floor(np.sqrt(features_count)), math.floor(features_count/3)]}

def random_forest_classifier(features, target):
    clf = RandomForestClassifier(n_estimators=50,criterion='gini' ,max_depth=20, max_features=2)
    clf.fit(features, target)
    return clf
    
trained_model_RF= random_forest_classifier(train_ind[features], train_dep[response])

```

### Conclusion

Even though there is not a high success rate with video games on platforms, this should not discourage future developers from starting campaigns on the platform. For many games, there will always be communities are that are possibly looking into the exact game that you wish to develop or is simply a passion project for you. With each project, a creator can only have so much control over certain aspects of their project and the limitations and goals that they set for themselves. Therefore, from this analysis, I think it will provide an insight on factors that they can control such as the goal amount as well as the time allotted to reach said funding goal. 

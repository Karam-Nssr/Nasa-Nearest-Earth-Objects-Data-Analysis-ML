# Nasa-Nearest-Earth-Objects-Data-Analysis-ML <br/>
## DataSet link: https://www.kaggle.com/datasets/ivansher/nasa-nearest-earth-objects-1910-2024/data <br/>
## *Used*: <br/>
- python 3.12.4 <br/>
- libraries: pandas,numpy,seaborn,matplotlib. <br/>
- modules: sklearn,imblearn. <br/>
## *In this project*: <br/>
- Data Analysis for a real-world dataset that tracks Nearest Earth Objects (NEOs)
observed by NASA from 1910 to 2024. The dataset contains 338,199 records, each representing
an object in space that has been monitored for its proximity to Earth. Some of these objects are
classified by NASA as "is_hazardous," indicating that they pose a potential danger to our planet. <br/>
- Exploratory Data Analysis(EDA) to create informative graphs that reveal patterns,trends, 
and potential correlations within the dataset. <br/>
## *problems i faced and how i solved it*: <br/>
- The Data had some missing values. <br/>
I fixed this by filling the numerical missing values using mean function. <br/>
- there were some duplicate object names with the same features nut different id. <br/>
I fixed this by dropping dublicates and keeping only the first name of an object in the subset 'name'. <br/>
- the column is-hazardous was imbalanced. <br/>
I fixed this using SMOTE and RandomForestClassifier. <br/>
- while working on the project i faced some "future warning" problems related to the deprecation warning in Seaborn, where the use of the palette parameter without specifying the hue parameter is deprecated and will be removed in future versions. <br/>
i fixed this by Assigning name to the hue parameter and by Setting legend=False since hue creates a legend, and it is not necessary in this case. <br/>
- A warning because of how pandas is handling chained assignments, and it indicates that the inplace=True method is being used on a copy of the DataFrame, not the original DataFrame. In pandas versions beyond 3.0, inplace=True will no longer modify the original object when chained assignments are involved. <br/>
I fixed this by simply not using Inplace=True. <br/>
- Couldn't use GridSearchCV because of how LARGE time it needs to be excuted...due to alot of parameters and data existing.
## *process*: <br/> 
1. Importing important libraries and Loading The Dataset. <br/> 
2. Detecting The issues within the dataset. <br/> 
3. Handling missing Values. <br/> 
4. Dropping Duplicates. <br/> 
5. Having a clear view for the dataset (like data types and data description). <br/> 
6. EDA: <br/>
  - Visualizing the Target Variable (is_hazardous) and detecting class imbalance. <br/>
  - Creating Visualizations for Key Features. <br/>
  - Analyzing Distributions of Numerical Features and creating Histograms. <br/>
  - Checking Correlations Between Features by generating a correlation matrix for numerical features to assess the relationships between them and using a heatmap       to visualize correlations and identify any strong positive or negative correlations. <br/>
  - using pairplot to explore features interactions. <br/>
7. Data Preprocessing: <br/>
  - Importing important modules. <br/>
  - Dropping the features that don't affect the prediction to save runtime. <br/>
  - Splitting the data to testing and training sets. <br/>
  - Handling imbalanced class using SMOTE. <br/>
  - Fixing The seaborn issues and future warnings. <br/>
8. Prediction Results. <br/>
9. Revealing Each Feature's Importance. <br/>
## Conclusions:
```
Balanced Accuracy: 0.7738166532936925
Classification Report:
               precision    recall  f1-score   support

       False       0.97      0.91      0.94      6204
        True       0.36      0.64      0.46       499

    accuracy                           0.89      6703
   macro avg       0.66      0.77      0.70      6703
weighted avg       0.92      0.89      0.90      6703
```
1. The model performs well for the majority is_hazardous=False, but struggles with the minority is_hazardous=True, as shown by the low precision (0.36) and F1-score (0.46) for the "True" class. <br/>
2. The high overall accuracy of 89% is driven by the correct classification of the majority class and is not reflective of the model's performance on the minority class. <br/>
3. The balanced accuracy of 77% indicates moderate handling of class imbalance. <br/>

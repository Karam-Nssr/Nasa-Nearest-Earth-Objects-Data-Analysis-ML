# Nasa-Nearest-Earth-Objects-Data-Analysis-ML
DataSet link: https://www.kaggle.com/datasets/ivansher/nasa-nearest-earth-objects-1910-2024/data
#Used:
-python 3.12.4
-libraries: pandas,numpy,seaborn,matplotlib .
-modules: sklearn,imblearn.
#In this project:
-Data Analysis for a real-world dataset that tracks Nearest Earth Objects (NEOs)
observed by NASA from 1910 to 2024. The dataset contains 338,199 records, each representing
an object in space that has been monitored for its proximity to Earth. Some of these objects are
classified by NASA as "is_hazardous," indicating that they pose a potential danger to our planet.
-Exploratory Data Analysis(EDA) to create informative graphs that reveal patterns,trends,
and potential correlations within the dataset.
#problems i faced and how i solved it:
-The Data had some missing values.
I fixed this by filling the numerical missing values using mean function.
-there were some duplicate object names with the same features nut different id.
I fixed this by dropping dublicates and keeping only the first name of an object in the subset 'name'.
-the column is-hazardous was imbalanced.
I fixed this using SMOTE and RandomForestClassifier.
-while working on the project i faced some "future warning" problems related to the deprecation warning in Seaborn, where the use of the palette parameter without specifying the hue parameter is deprecated and will be removed in future versions.
i fixed this by Assigning name to the hue parameter and by Setting legend=False since hue creates a legend, and it is not necessary in this case.
-A warning because of how pandas is handling chained assignments, and it indicates that the inplace=True method is being used on a copy of the DataFrame, not the original DataFrame. In pandas versions beyond 3.0, inplace=True will no longer modify the original object when chained assignments are involved.
I fixed this by simply not using {Inplace=True}

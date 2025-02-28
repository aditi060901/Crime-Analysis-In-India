Introduction

Crime is a complex and persistent issue that affects societies globally, impacting quality of life, economic stability, and overall public safety. Cities with similar demographic and 
socio-economic profiles often exhibit comparable crime 
patterns, making it essential to understand and predict these 
patterns for proactive crime prevention and efficient resource 
allocation. Traditional approaches to crime analysis have relied 
heavily on historical crime data and statistical methods, which, 
while insightful, lack the predictive power required to inform 
dynamic urban safety strategies. 
In recent years, machine learning (ML) has emerged as a 
powerful tool for analyzing large datasets and uncovering 
intricate patterns that would be challenging to detect manually. 
Leveraging ML techniques, this study focuses on identifying 
cities with similar crime trends by clustering them based on 
various types of crime and then classifying new cities into 
these clusters. This approach allows for a more nuanced 
understanding of crime patterns across different regions, help- 
ing policymakers and law enforcement agencies to deploy 
resources effectively and implement targeted crime prevention 
measures.  
The proposed model operates in two primary stages.  In the 
first stage, cities are grouped into clusters based on crime type 
frequencies using clustering algorithms. These clusters 
represent cities with analogous crime patterns, which enables 
comparisons across cities and provides a foundation for 
pattern-based crime prediction. In the second stage, classi- 
fication algorithms—including Random Forest, Naive Bayes, 
Decision Tree, and Logistic Regression—are trained to predict 
the cluster assignment of a city based on its crime statistics. 
The model demonstrated that Random Forest achieved the 
highest prediction accuracy, reaching 93%, underscoring its 
effectiveness in crime pattern recognition. By identifying 
clusters of cities that follow crime trends similar to prominent 
cities, this model enables a strategic approach to crime 
prevention. When a city is classified into a specific cluster, it 
allows policymakers to apply interventions based on similar 
cities’ experiences. This approach is particularly beneficial for 
identifying emerging crime patterns in smaller or less-studied 
cities by drawing parallels with major urban centers. 

Process Flow

A. Data Collection  
The dataset for the crime analysis project is exclusively 
sourced from Kaggle, covering crime data from various 
cities in India for the years 2020 to 2024. This dataset 
encompasses a wide range of information, including the 
type of crime, location, time of occurrence, and 
demographic factors. The comprehensive nature of this 
dataset allows for an in-depth analysis of crime patterns, 
helping to identify similarities in criminal activity across 
different urban areas. This focused dataset serves as the 
foundation for understanding crime trends and their 
correlations throughout the country. 

B. Data Preprocessing  
Data preprocessing is a critical phase in analyzing crime 
data, aimed at enhancing data quality and ensuring its 
readiness for insightful analysis. This process involves 
several key steps to address issues related to data 
integrity and format. Initially, the dataset is examined 
for duplicate rows, which are then eliminated to 
maintain the uniqueness of each record. Missing values 
are identified, and empty strings are replaced with NaN 
to facilitate proper data handling. Furthermore, date 
columns, such as 'Date Reported' and 'Date of 
Occurrence,' are converted to datetime format, enabling 
easier manipulation and analysis of temporal data. 
Unnecessary columns that do not contribute to the 
analysis—such as 'Time of Occurrence,' 'Weapon Used,' 
'Police Deployed,' 'Crime Code,' and 'Report Number'—
are subsequently removed to streamline the dataset. 
This comprehensive preprocessing approach ensures 
that the data is clean, structured, and primed for 
effective exploratory data analysis and modeling, 
ultimately leading to more accurate insights into crime 
patterns. 

C. Clustering Cities by Crime Patterns 
K-means clustering is used to group cities based on 
similarities in crime profiles. The crime statistics 
(frequency of each crime type) are treated as features, 
and the optimal number of clusters is determined using 
the Elbow Method. This method involves plotting the 
within-cluster sum of squares against the number of 
clusters to identify the point where the rate of decrease 
slows significantly. The cities within each cluster are 
those that exhibit similar crime distributions, making it 
possible to identify groups of cities that share 
comparable crime patterns. 

D. Model Training and Testing 
The model is trained to identify the group of cities to 
which a particular city belongs by taking in crime 
statistics as input. The dataset is divided into train and 
test subsets. Classification algorithms: Random Forest, 
Logistic Regression, Naïve Bayes and Decision Tree 
are applied on the training dataset. The clusters 
assigned is considered target and the crime statistics as 
features. Test dataset is passed to the models and 
evaluation metrics: accuracy, precision, recall and F1
score are calculated. 

E. Cross Validation  
To ensure balanced evaluation across clusters, 
stratified cross-validation is used in this study. Unlike 
standard cross-validation, stratified cross-validation 
maintains the proportion of each cluster in every fold, 
ensuring that each fold is representative of the entire 
dataset's distribution of crime pattern clusters. 
Stratified k-fold cross-validation with 5 folds is 
applied to evaluate the performance of the 
classification models. 

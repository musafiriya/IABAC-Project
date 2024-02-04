# IABAC-Project
1)Business Case:
INX Future Inc ,(referred as INX ) , is one of the leading data analytics and automation solutions provider with over 15 years of global business presence. In recent years, the employee performance indexes are not healthy and this is becoming a growing concerns among the top management. There has been increased escalations on service delivery and client satisfaction levels came down by 8 percentage points.The CEO of company decided to analyse the current employee data and find the core underlying causes of this performance issues of the employees. Company also expects a clear indicators of non performing employees, so that any penalization of non-performing employee, if required, may not significantly affect other employee morals.

The following insights are expected from this project.

1. Department wise performances

2. Top 3 Important Factors effecting employee performance

3. A trained model which can predict the employee performance based on factors as inputs. This will be used to hire employees

4. Recommendations to improve the employee performance based on insights from analysis

2)Requirement
Data from third party sources. The employee performance data of INX Future Inc. can be downloads from below link. http://data.iabac.org/exam/p2/data/INX_Future_Inc_Employee_Performance_CDS_Project2_Data_V1.8.xls

3)Analysis
The data is supervised and categorical as well as numerical, we have 19 Numerical features and 9 categorical features. The predictor variables are nominal and ordinal. The target variable 'PerformanceRating' is ordinal.

Feature Analysis

EmpNumber-Unique ID number of employee
Age - Age of the employee
Gender - Gender of the employee
EducationBackground - Educatiocation background of the employee
MaritalStatus - Married,unmarries or divorced
EmpDepartment - The department of the employeee
EmpJobRole-Job role of the employee(Sales executive,Developer etc)
BusinessTravelFrequency - If business travelling there,how frequent it is ?
DistanceFromHome - Distance of employee home to company
EmpEducationLevel -Education level means is highest education level of the employee
EmpEnvironmentSatisfaction - Working environmrent Satisfaction rating of employees
EmpHourlyRate-Hourly rate he is receiving
EmpJobInvolvement - Involment in job in a scale of 4
EmpJobLevel - Job level of employees in a scale of 4
EmpJobSatisfaction- Satisfaction of employees in thier job
numCompaniesWorked - Number of company worked previously
OverTime - Overtime is there or not??
EmpLastSalaryHikePercent - Last salary hike percentage of employees
EmpRelationshipSatisfaction - Satisfaction with employer relationship in scale of 4
TotalWorkExperienceInYears - Total work experience in years
TrainingTimesLastYear - No of trainings attented last year
EmpWorkLifeBalance - Worklife balance of employees in a ring of 4
ExperienceYearsAtThisCompany -No of years experienccce in the current company
ExperienceYearsInCurrentRole - No of years experienccce in the currentjob role
YearsSinceLastPromotion - Last promtion year of employees
YearsWithCurrManager -No of years with the current manager
Attrition - employee left the company or not
PerformanceRating -Target column is Performance rating of the employees (2-low,3-Good,4-High)

Exploratory data analysis

For Univariate and Bivariate analysis Seaborn,Matplotlib libraries are used..
Pie chats
histogram
boxplots
barcharts
countplots

UNIVARIANT ANALYSIS

Average age of employee in the INX Future Inc is 36 whereas the maximum employee lies in the age group of 25 to 45.

Many employees resides near the office.

Many employees has given rating as 3.0 for employee job environment.

Many employees has worked for 0-1 company.

most of the employee got salary hike of 0-12%.

most of the employee has given performance rating as 3.

BIVARIANT ANALYSIS

We can conclude that from EmpDepartement Development department is showing high performance rate as compared to other departement.

After development department Research & Development department performed well.Sales,Human resources, data science and finance also performed well.

employee which are business analyst, technical lead, data scientist, developer,have performed well performance rating of employee does not vary with Marital status employee who do overtime have rated as more as compared to those who doesn't do overtime.

Employee with gender as male are rated more as compare to female employee, the reason may be there are more number of male employees than female employees in the company.

Employees with education background of Life science and medical are rated more

Employee who travel rarely are rated more as compared to those who travel frequently or who are non traveler

Performance rating of employee depends on Years with current manager.when manager is same for long duration of time the employee performace drops. So, for improving performance of employee the manager needs to shuffle atleast after every 2-3 years.

performance rating depends on years since last promotion. when employee are not promoted since 2 to 3 years, the perfromance of employee drops. Hence to imporve performace of employee the employee should be promoted after every 1 year or at least 2 years.

Performace of employee also depends on employee work life balance. when employee work life balance is good and are rated as 3 the performance rating of employee is also more.

when employee relationship satisfaction is more the performance of employee is also more

When total work experience of employee is above 10 year the performace of employee drops

when the employee got salary hike of more than 19%, the performce of employee increased. thus, employee performace depends on the salary hike given by the company. employee with higher salary hike percentage has performed well.

employee who are satisfied by environment have performed well.

We can see that 11% and 16.3% of employees having low job satisfaction and job involvement have low performance ratings

These are mainly used for visual representation of data ..

The data contains 1200 rows and 28 columns

Numerical columns -Age,Distance From Home,Employee Hourly Rate,Num Companie sWorked,Emp Last Salary Hike Percent, Total Work Experience In Years,Experience Years At This Company,Training Times Last Year,Experience Years in Current Role, Years Since Last Promotion,Years With Current Manager

Categorical columns - Gender, Education Background,Marital StatusEmp Education Level,Emp Environment Satisfaction, Emp Job Involvement, Emp Department, Emp Job Role, Business Travel Frequency,Emp JobLevel,Emp Job Satisfaction,OverTime', Emp Relationship Satisfaction,Emp Work Life Balance,Attrition

While checking descriptive statistical details it indicates maximum value of most of the numerical columns are far away from its Mean and Median

There are many categorical columns are there... Most of the numerical columns are positively skewed distributions..

There is no constant columns(std=0)

Data preprocessing

asic Checks - No null values

Conversion of Categorical Data: Handeled categorical by using mannual encoding,one hot ending and Label encoding

For outlier treatment Median imputation and Quantile based flooring & capping – (In this technique, the outliers are capped at a certain value above 90th percentile or floored at a factor below the 10th percentile) are used..Most of outliers are handled by imputing medians.

Checking Null values:- There are no null values

Categorical to Numerical data conversion:- Handle categorical data to Numerical using Label encoding.

Outlier Handling:- Some features contains outliers so we are imputing these outliers with the help of IQR and 3 sigma rule. If the features are normally distributed we will use 3 sigma rule. If the features are not normally distributed we will use IQR.

Feature Transformation:- In YearsSinceLastPromotion some skewed & kurtosis is present, so we used Square Root Transformation techinque.

Scaling the data:- Scaling the data with the help of Standard scalar.

Standard Scaling: Standardization is the process of scaling the feature, it assumes the feature follow normal distribution and scale the feature between mean and standard deviation, here mean is 0 and standard deviation is always 1.

Feature Selection
There are lot of features in our dataset, to extract important features which really contribute to target feature we need to find corelation coefficient. Corelation coefficient is used to find out the important features in dataset and these features are then used to train the model.

From there, we also get the top factors which affect performance. We can see that the most important features selected were Department, Job Role, Environment Satisfaction, Last Salary Hike Percent, Work Life Balance, Experience Years At This Company, Experience Years In Current Role, Years Since Last Promotion, Years With Current Manager. These were selected because their correlation coeffecient with Performance Rating was more than 0.1.

Standarization and Label Encoding was also used for feature transformation.

Numerical features are selected by using pearson correlation heatmap..But there are no highly correlated features are not there

The experience in the current role and years with manager are having the higher correlation with each other.
Experience years at this company and years with manager also have a good positive correlation.
Experience years at this company and The experience in the current role also have a good positive correlation
For categorical feature selection i adopted chi square test and p value..Except job satisfaction column,Features with higher p value gets removed..From the data analysis it is clealry visible that job satisfaction is an important feature.. When company wants to find its employee performance ,this feature should definetly consider.. Columns with low chi square score

Gender,Business Trave Frequency,Education Background,Emp Education Level,Emp Job Involvement, Emp Relationship Satisfaction,marital Status,Attrition

Data Normalization-

Min Max scaler - Min Max scaler is sclaing technique that scales all the data features in the range [0, 1]. Values of columns have years,kilometers,hourly rate etc..,values of these columns are different numeric figures....MinMaxScaler preserves the shape of the original distribution,it doesn’t meaningfully change the information embedded in the original data.Most of the columns are poitively skewed even after outlier treatment,the data set is small and treating outliers to a certain extend may leads to change in the total behaviour and pattern

Data Balancing-

SMOTE() - It is an oversampling technique aims to balance class distribution by randomly increasing minority class examples by replicating them.Our data is highly imbalanced (72% :17% :11%) and any model without balancing would be a dump model..For balancing the data i used SMOTE() oversampling technique..

We can conclude that top 3 Important Factors affecting employee performance are-

1)Employee EnvironmentSatisfaction,

2)Employee Last Salary Hike Percent and

3)EmpWorkLifeBalance

Drop unique and constant feature: Dropping employee number because this is a constant column as well as drop Years Since Last Promotion because we create a new feaure using square root transformation

Checking Correlation: Checking correlation with the help of heat map, and get the their is no highly correlated feature is present. Heatmap: A heatmap is a graphical representation of data that uses a system of color-coding to represent different values.

Check Duplicates: In this data Their is no dupicates is present.

Machine learning Model Creation & Evaluation
Define Dependant and Independant Features:

Balancing the data: The data is imbalance, so we need to balance the data with the help of SMOTE SMOTE: SMOTE (synthetic minority oversampling technique) is one of the most commonly used oversampling methods to solve the imbalance problem. It aims to balance class distribution by randomly increasing minority class examples by replicating them. SMOTE synthesises new minority instances between existing minority instances.

In the model building part,

Evaluation Metrics-
Weighted F1 SCORE - we are taking f1 score as the performance metrics,f1 score is the harmonic mean of precision and recall..
why weighted f1 score?? Data is highly imbalanced (72% :17% :11%) and applying an algoithm with this data leads to overfit and missclassfication will occur..Too avoid this problem we applied some SMOTE techniques and selects evaluation metric as Weighted F1 score for checking the performance of our model...
Precision and Recall- The percentage of true positive rate and False positive rate
Confusion Matrix - To know the classfication in each classes, FPR and FNR and its perncetage,in which extend overfitting occurs
I tried with 8 base models and based on the performance selected top 4 models for tuning

Random Forest Classifier - It is a supervised learning algorithm and It is basically a set of decision trees (DT) from a randomly selected subset of the training set and then It collects the votes from different decision trees to decide the final prediction.In our model building at first, the Random model overfits with default paramters.The main reason is imbalanced data set but with a good weighted f1 score of 94%..But it in real life scenario this model will not work well due to its high variance...So i tried for a generalized model that produces a result with low varaince and low bais..After hyper paramter tuning score is 93% with very minimal presense of overfitting..

Catboost Classifier- It is a boosting supervised machine learning algorthm mostly work with categorical data ..But the model overfits even after hyper paramter tuning

XGB and Gradient Boosting - These are another boosting algorithms used for model building..Both the both models give good result of 92%

For hyper paramtertuning i used
GridSearch CV-(is the process of performing hyperparameter tuning in order to determine the optimal values for a given model.)
Kfold Cross validation-(It is data partitioning strategy) It really helps to avoid overfitting problem and helps to build the model is a generalized one.
Tried but Failed !!!!*

For hyper parameter tuning i tried Randomized SesrchCV but result was not upto the mark...
Models like decsion tree,logistic regression and SVM also didnot give good results
Unsupervised model of PCA is also tried ,result was poor and it was not addressed the relevent features
Also tried Hard outlier handling and square root tranformation,but it resulted very poor model..
At first Plotly and hvplots libraries are used but due to file size issue changed to Seaborn and Matplotlib libraries

Splitting Training And Testing Data: 75% data use for training & 25% data used for testing

Algorithm:
AIM: Create a sweet spot model (Low bias, Low variance)

HERE WE WILL BE EXPERIMENTING WITH THREE ALGORITHM

Logistic Regression

Support Vector Machine

Random Forest

Decission Tree

Artificial Neural Network MLP classifier

Support vector machine well perform on training data with accuracy 90% but the test score is 87%.
Random forest very well perform in training data with 100% accuracy but in testing 97.61% after doing hyperparameter tunning testing score is decreases.

Artifical neural network[Multilayer percepton] perform very well on training data with 99% accuracy and testing score is 91.80%.

So we are selecting Random forest model.

Recommendations to improve the employee performance
The overall employee performance can be achieved by employee environment satisfaction. The company needs to focus more on the employee environment satisfaction.

shuffling the manager after every 2-3 years will result in good performance of employee.

The salary hike will give the boost to the employees to perform well.

Promote the employee every 6th month

Improve Employee's work-life balance this affects the performance rating.

While recruiting for HR, consider the female candidates where they perform well compared to male.

The development and sales department is having an overall higher performance comparing to rest of the departments. While some of the employees who gives feedback like Low & Medium from Job Satisfaction & Relationship Satisfaction feature, such employees gives Excellent performance more in number. So company should focus on them.

Algorithm:
AIM: Create a sweet spot model (Low bias, Low variance)

HERE WE WILL BE EXPERIMENTING WITH THREE ALGORITHM

Logistic Regression
Support Vector Machine
Random Forest
Decission Tree
Artificial Neural Network MLP classifier
Support vector machine well perform on training data with accuracy 90% but the test score is 87%.
Random forest very well perform in training data with 100% accuracy but in testing 97.61% after doing hyperparameter tunning testing score is decreases.
Artifical neural network[Multilayer percepton] perform very well on training data with 99% accuracy and testing score is 91.80%.
So we are selecting Random forest model.

Recommendations to improve the employee performance
The overall employee performance can be achieved by employee environment satisfaction. The company needs to focus more on the employee environment satisfaction.
shuffling the manager after every 2-3 years will result in good performance of employee.
The salary hike will give the boost to the employees to perform well.
Promote the employee every 6th month
Improve Employee's work-life balance this affects the performance rating.
While recruiting for HR, consider the female candidates where they perform well compared to male.
The development and sales department is having an overall higher performance comparing to rest of the departments. While some of the employees who gives feedback like Low & Medium from Job Satisfaction & Relationship Satisfaction feature, such employees gives Excellent performance more in number. So company should focus on them.

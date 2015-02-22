# Getting-and-Cleaning-Data

Data Set Information:

I used the information provided from http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones to help summarize the experiment.

"The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain."


Attribute Information:

For each record in the dataset it is provided: 
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration. 
- Triaxial Angular velocity from the gyroscope. 
- A 561-feature vector with time and frequency domain variables. 
- Its activity label. 
- An identifier of the subject who carried out the experiment.

n order to create a raw data set, the following regular expression was used: -(mean|std)[(]. I.e. all variables containing -mean( or -std( in their names were filtered.

Totally, the raw data set contains 68 variables:

subject - An identifier of the subject who carried out the experiment.
label - An activity label.
Plus 66 filtered features mined as described below.



These signals were used to estimate variables of the feature vector for each pattern:
-XYZ is used to denote 3-axial signals in the X, Y and Z directions.

tBodyAcc-XYZ
tGravityAcc-XYZ
tBodyAccJerk-XYZ
tBodyGyro-XYZ
tBodyGyroJerk-XYZ
tBodyAccMag
tGravityAccMag
tBodyAccJerkMag
tBodyGyroMag
tBodyGyroJerkMag
fBodyAcc-XYZ
fBodyAccJerk-XYZ
fBodyGyro-XYZ
fBodyAccMag
fBodyAccJerkMag
fBodyGyroMag
fBodyGyroJerkMag
The set of variables that were estimated from these signals are:

mean(): Mean value
std(): Standard deviation

mean(): Mean value
std(): Standard deviation

The tidy data set contains the same variables as the raw does, but I renamed the variables. These were the changes made:

All lower case when possible - the variables names were not converted to lower case, since it would make them unreadable. Instead, the variable names were converted to satisfy camlCase rule.
Descriptive (Diagnosis versus Dx) - the variable names are descriptive, so nothing special should be done.
Not duplicated - the variable names are unique, so again nothing special had to be done.
Not have underscores or dots or white spaces - dashes and parentheses were removed from variable names.
To satisfy the requirements above, the following replacements were performed:

Replace -mean with Mean
Replace -std with Std
Remove characters -()
Replace BodyBody with Body


---
title: "Codebook"
author: "OlveraH"
date: "3/10/2020"
---
## Overview
The run_analysis.R script performs the data preparation and then followed by the 5 steps required as described in the course project’s assignment.

#### 1. Download the dataset
Dataset downloaded and extracted under the folder called UCI HAR Dataset

#### 2. Assign each data to variables
- features <- features.txt : 561 rows, 2 columns.
Features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
- activities <- activity_labels.txt : 6 rows, 2 columns.
Activities performed when the corresponding measurements were taken and its codes (labels).
- subject_test <- test/subject_test.txt : 2947 rows, 1 column.
Test data of 9/30 volunteer test subjects.
- x_test <- test/X_test.txt : 2947 rows, 561 columns.
Recorded features test data.
- y_test <- test/y_test.txt : 2947 rows, 1 columns.
Test data of activities code labels.
- subject_train <- test/subject_train.txt : 7352 rows, 1 column.
Train data of 21/30 volunteer subjects being observed.
- x_train <- test/X_train.txt : 7352 rows, 561 columns.
Recorded features train data.
- y_train <- test/y_train.txt : 7352 rows, 1 columns.
Train data of activities’code labels.

#### 3. Merges the training and the test sets to create one data set
- X: created by merging x_train and x_test using rbind() function.
- Y: created by merging y_train and y_test using rbind() function.
- Subject: created by merging subject_train and subject_test using rbind() function.
- Merged: created by merging Subject, Y and X using cbind() function

#### 4. Extracts only the measurements on the mean and standard deviation for each measurement.
- TidyData: created by subsetting Merged_Data, selecting only columns: subject, code and the measurements on the mean and standard deviation (std) for each measurement.

#### 5. Uses descriptive activity names to name the activities in the data set
- Entire numbers in code column replaced with corresponding activity taken from second column of the activities variable.

#### 6. Appropriately labels the data set with descriptive variable names.
- code column in TidyData renamed into activities.
- Acc in column’s name replaced by Accelerometer.
- Gyro in column’s name replaced by Gyroscope.
- BodyBody in column’s name replaced by Body.
- Mag in column’s name replaced by Magnitude.
- f in column’s name replaced by Frequency.
- t in column’s name replaced by Time.

#### 7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
- FinalData: created by sumarizing Tidy taking the means of each variable for each activity and each subject, after groupped by subject and activity.
Export Final into Final.txt file.

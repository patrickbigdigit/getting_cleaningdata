---
title: "Codebook.md"
output: html_document
---

CodeBook

This is a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data.
The data source

    Original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
    Original description of the dataset: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Data Set Information

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.
The data

The dataset includes the following files:

    1. 'README.txt'
    2. 'features_info.txt'
    3. 'features.txt'
    4. 'activity_labels.txt'
    5. 'train/X_train.txt'
    6. 'train/y_train.txt'
    7. 'test/X_test.txt'
    8. 'test/y_test.txt'


Coding details is mentioned below. 

Five different activities have been performed on the dataset to convert tidy dataset as per the project requirement. 1.

    1. Merges the training and the test sets to create one data set.
    2. Extracts only the measurements on the mean and standard deviation for each measurement.
    3. Uses descriptive activity names to name the activities in the data set
    4. Appropriately labels the data set with descriptive activity names.
    5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject.

How run_analysis.R implements the above steps:

Assumes that, current working directory is set properly and dataset is unzipped as .\UCI HAR Dataset\ directory. 

    1. Require data.table and dplyr librareis.
    2. Load both test and train data. (downloading dataset and unzip is not covered in the source script)
    3. Load the features and activity labels.
    4. Extract the mean and standard deviation column names and data and discard the other variables. 
    5. Process the data. There are two parts processing test and train data respectively.
    6. Merge data set and prepare a tidy data set by calculating mean of all variables for the grouped dataset using summarize_each function. 
    7. Export/Write Tidy data into a text file for later export. 


# CodeBook
## Steps / explaination for run_analysis.R

### Q1
#### (Merges the training and the test sets to create one data set.)
1. Reading the datasets in the test and train folder
2. combinding the subject dataset, x train/test

###Q2
#### (Extracts only the measurements on the mean and standard deviation for each measurement.)
1. reading the file features.txt 
2. using grep to find the index where text in the second column of the dataframe that contain mean or std (66 match)
3. creating a new dataframe for measurements that only have the column containing mean or std. (10299 by 66)


### Q4
#### (Appropriately labels the data set with descriptive variable names.)
1. Getting the names from features.txt (ie such as tBodyAcc-mean()-X)
2. labeling the columns of the dataframe in Q2 step 3 by the names in featuers.txt
3. combining this dataframe with dataframe for person and activity label. 

### Q3
#### (Uses descriptive activity names to name the activities in the data set)
1. reading the file activity_labels.txt
2. merging the activity name in activity_labels.txt with the corresponding number in the combined dataset


### Q5 
#### (From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.)
1. using the dataset in Q4
2. applying aggregate to the dataset, and finding the mean measurement of each columns  for each person for each activity. 
3. merging the activity name (as applying the mean to the dataset takes away the text)
4. take away some extra columns created while merging. Ending up with 180 by 69 data frame. 180 as there are 30 person and 6 activities for each person. 
5. writing the new table in to a txt file. 


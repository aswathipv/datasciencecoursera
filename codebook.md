Smartphone Data Cleaning And Exploration Code Book
All of the analysis is done in run_analysis.R script. Following is the description of variables, data, and transformations methods or work performed in each step for analysis.

Step 1 - Merges the training and the test sets to create one data set
Reads all unique column or variable names from "features.txt" file into colNames variable.
Reads training data from "UCI HAR Dataset/train/X_train.txt" file into trainData variable.
Reads training data from "UCI HAR Dataset/train/X_test.txt" file into testData variable.
Merges or conactenates the testData and trainData into testTrainMerged variable.
Reads subject test data from "UCI HAR Dataset/test/subject_test.txt" file into subjectTestData variable.
Reads subject train data "UCI HAR Dataset/train/subject_train.txt" file into subjectTrainData variable.
Merges the both training and test for subject into subjectDataMerged variable.
Step 2 - Extracts only the measurements on the mean and standard deviation for each measurement
Gets all of the columns / variables from colNames variable that have mean or std in their name into meanStdCols variable.
Gets the subset of the data from testTrainMerged variable by specifying column names using meanStdCols variable and sets meanStdData variable with this subset of data.
Step 3 - Uses descriptive activity names to name the activities in the data set
Reads test data activity ids from "UCI HAR Dataset/test/y_test.txt" file into testActivityId variable.
Reads train data activity ids from "UCI HAR Dataset/test/y_train.txt" file into trainActivityId variable.
Merges both the above activity ids into activityIdsMerged variable.
Reads the activity names from the "UCI HAR Dataset/activity_labels.txt" file into activityLabels variable.
Converts activityIdsMerged variable into a factor variable to get levels.
Sets ids in activityIdsMerged variable with corresponding activity names in activityLabels variable.
Step 4 - Appropriately labels the data set with descriptive variable names
Does a column wise Merging of subject, activity and other test and train data extracted in previous steps into finalData variable.
Column Names in finalData variable are renamed.
Step 5 - From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject
Calculate mean of all the columns.
Groups the data by Subject Id and Activity Name.
Export result in analysis_result.txt file using write.table function.

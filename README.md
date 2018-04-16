# project_task1
Repository for task 1 of project 1

Below are the steps to completing task 1.

1)	Read “train_activities.txt”, “X_train.txt”, “test_acivities.txt”, “X_test.txt”, “subject_train.txt”, “subject_test.txt”, and “features.txt” into their own data frames using read.table()
2)	Convert each of the above data frames to a data type that is workable with the dplyr package using tbl_df(). Store each in a new variable. 
3)	Bind the x training data on top of the x testing data using rbind()
4)	Use the variable containing feature names, created above, to name the columns of the x data. Use the names() function to do this.
5)	With the x data named by column, extract the mean and standard deviation measurements with the select() function and three arguments: the dataset from which you are selecting, and two iterations of the contains() function- one for “-mean” and one for “-std”.
6)	Bind the y training data on top of the y testing data, and store in a new variable.
7)	Bind the subsetted x data to the y data to form a new, complete dataset with every observation still intact, but only the relevant columns. 
8)	Create a variable for each subject, 1-30, that is a subset of the complete data set. These thirty variables should contain every column from the complete dataset.
9)	For each Subject number, create a new variable to subset based on activity. .  This results in six new variables for each subject. Use the subset function as follows: subset(x, Activity == “___”, select = 3:81). Subset only columns 3 – 81 because the ensuing colMeans() function can only take the mean of numerical values.  From these six new variables, use colMeans() to find the mean of each column.
10)	 After creating variables with column means for each combination of subject and activity (180 total), bind them by activity for each subject. For example, subject 1 should be bound with all six activities, then subject two and so on. Create thirty datasets, one for each subject number, of 6 observations each. Use rbind() to do this.
11)	 Use rbind() again to bind the thirty datasets created in step 10. 
12)	Because this dataset is only the numerical values, or columns 3-81 from the earlier “complete data” variable, we now need to add proper Subject and Activity columns. 
13)	 Create an array of subject names with 6 of each number from 1-30, in order. It should start c(1,1,1,1,1,1,2,2,2,2,2,2,3,….)
14)	Create an array for activity names with the following sequence repeating 30 times: "Walking", "Walking_Upstairs","Walking_Downstairs", "Sitting", "Standing", "Laying".
15)	 Convert both the subject names and the activity names arrays into data frames with tbl_df().
16)	Rename the columns of those data frames “Subject” and “Activity”, respectively, with the names() function. 
17)	Bind the subject names data frame (1 variable, 180 obs), the activity names data frame (1 variable, 180 obs), and the data frame of column means (79 variables, 180 obs). This should create a data frame of 180 observations and 81 variables. 
18)	Use the write.table() function to create a .txt file of the final data frame. 

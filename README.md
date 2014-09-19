README
======

This README file accompanies the **Final Project** for the course "*Getting and Cleaning Data*". 

**Data specification can be found on [this Github repository](https://github.com/ProfCLC/GettingAndCleaningData) in the *CodeBook.md* file**

##Goals of the Project

The goals of this project are fully explicatd by the course instructor  [here](https://class.coursera.org/getdata-007/human_grading/view/courses/972585/assessments/3/submissions).  The task is to create one R script called *run_analysis.R* that does the following:

1. Merge the training and the test data sets to create one data set
2. Extract only the measurements on the mean and standard deviation for each measurement 
3. Use descriptive activity names to name the activities in the data set
4. Appropriately label the data set with descriptive variable names 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject

##Dependencies Required for Running the R Script
`run_analysis.R` had two dependencies: `data.table` and `reshape2`. The program first checks for these packages and then installs and initializes them prior to running the rest of the script.

###Other Requirements and Information
* The user is reminded to properly set the working directory using `setwd()` and to install `run_analysis.R` into the working directory
* `run_analysis.R` will check for a *data* folder and then will create such a folder if it does not already exist in the working directory
* The script should be placed into the *data* folder
* The script can be run using the `submit(source("run_analyis.R"))` command at the R prompt or by sourcding and submitting in a way commonly done by the end user


##How `run_analysis.R` Implements the Project Goals

1. Checks for and creates, if necessary, a *data* folder in the working directory
2. Checks for and installs, if necessary, `data.table` and `reshape2`
3. Downloads the zipped data file and stores it in the *data* folder (see the *CodeBook.md* file for information about the data and the zipped file
4. Reads the *features* and the *labels* data files
5. Reads the *test* data files and binds these files together
6. Reads the *training* data files and binds these files together
7. Binds the *test* and the *training* data together
8. Adds the labels to the combined data set using the `melt` command
9. Uses `dcast` to cast the final table and to implement the `mean` function
10. Uses the `write.table` command to produce the final *tidy data* file ('tidy_data.txt')

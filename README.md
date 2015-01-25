# datacleaning
This is for submission for classwork

run_analysis programs without passing any parameters. run_analysis() can be run R prompt after setting the setwd() to the root of the data source i.e where the "UCI HAR Dataset" directory resides. The directory where the run_analysis() should be run should contain the "UCI HAR Dataset" folder (as the file is unzipped). Off course, all the subsequently directories such as train and test should be presevered from zipped version. 

The run_analysis reads the data in the following manner. 

Step 1: Reads the activity labels (code) with activity description - function readactivitylabels()
Step 2: Reads the 561 features - function readfeatures()
Step 3: Reads the Y Data from both test and train and joins with the corresponding activity labels - function - readY(activitylabels) #input of activity labels
Step 4: Reads the X data from both test and train and retains the columns which contain mean and std in the thier names. It also merges data with Y data to complete dataset. - function readX(yData, featureList) - #incput in Y Data from Step 3 and Feature List from Step 2. 
Step 5: Reads the subject data from the train and test and merges with X data from step 4. 
Step 6: The run_analysis function does a group_by and summarize_each() to get the tidy dataset

The Acticity Labels are as follows: 
Activity.ID	Activity.Description
1	1	WALKING
2	2	WALKING_UPSTAIRS
3	3	WALKING_DOWNSTAIRS
4	4	SITTING
5	5	STANDING
6	6	LAYING

Outtput of Tidy Dataset is as follows: 

Subject.ID is indentifyer for the subject
Activity.Description is descripton of actvity as above

The rest of columns that have mean and std in thier names and mean from the individial values. Each subject (30 in all) have one mean for each of activity (6 activites in all). so, there are 180 rows of data in the tidy dataset.

[1] "Subject.ID"                           "Activity.Description"                 "tBodyAcc.mean...X"                   
 [4] "tBodyAcc.mean...Y"                    "tBodyAcc.mean...Z"                    "tGravityAcc.mean...X"                
 [7] "tGravityAcc.mean...Y"                 "tGravityAcc.mean...Z"                 "tBodyAccJerk.mean...X"               
[10] "tBodyAccJerk.mean...Y"                "tBodyAccJerk.mean...Z"                "tBodyGyro.mean...X"                  
[13] "tBodyGyro.mean...Y"                   "tBodyGyro.mean...Z"                   "tBodyGyroJerk.mean...X"              
[16] "tBodyGyroJerk.mean...Y"               "tBodyGyroJerk.mean...Z"               "tBodyAccMag.mean.."                  
[19] "tGravityAccMag.mean.."                "tBodyAccJerkMag.mean.."               "tBodyGyroMag.mean.."                 
[22] "tBodyGyroJerkMag.mean.."              "fBodyAcc.mean...X"                    "fBodyAcc.mean...Y"                   
[25] "fBodyAcc.mean...Z"                    "fBodyAcc.meanFreq...X"                "fBodyAcc.meanFreq...Y"               
[28] "fBodyAcc.meanFreq...Z"                "fBodyAccJerk.mean...X"                "fBodyAccJerk.mean...Y"               
[31] "fBodyAccJerk.mean...Z"                "fBodyAccJerk.meanFreq...X"            "fBodyAccJerk.meanFreq...Y"           
[34] "fBodyAccJerk.meanFreq...Z"            "fBodyGyro.mean...X"                   "fBodyGyro.mean...Y"                  
[37] "fBodyGyro.mean...Z"                   "fBodyGyro.meanFreq...X"               "fBodyGyro.meanFreq...Y"              
[40] "fBodyGyro.meanFreq...Z"               "fBodyAccMag.mean.."                   "fBodyAccMag.meanFreq.."              
[43] "fBodyBodyAccJerkMag.mean.."           "fBodyBodyAccJerkMag.meanFreq.."       "fBodyBodyGyroMag.mean.."             
[46] "fBodyBodyGyroMag.meanFreq.."          "fBodyBodyGyroJerkMag.mean.."          "fBodyBodyGyroJerkMag.meanFreq.."     
[49] "angle.tBodyAccMean.gravity."          "angle.tBodyAccJerkMean..gravityMean." "angle.tBodyGyroMean.gravityMean."    
[52] "angle.tBodyGyroJerkMean.gravityMean." "angle.X.gravityMean."                 "angle.Y.gravityMean."                
[55] "angle.Z.gravityMean."                 "tBodyAcc.std...X"                     "tBodyAcc.std...Y"                    
[58] "tBodyAcc.std...Z"                     "tGravityAcc.std...X"                  "tGravityAcc.std...Y"                 
[61] "tGravityAcc.std...Z"                  "tBodyAccJerk.std...X"                 "tBodyAccJerk.std...Y"                
[64] "tBodyAccJerk.std...Z"                 "tBodyGyro.std...X"                    "tBodyGyro.std...Y"                   
[67] "tBodyGyro.std...Z"                    "tBodyGyroJerk.std...X"                "tBodyGyroJerk.std...Y"               
[70] "tBodyGyroJerk.std...Z"                "tBodyAccMag.std.."                    "tGravityAccMag.std.."                
[73] "tBodyAccJerkMag.std.."                "tBodyGyroMag.std.."                   "tBodyGyroJerkMag.std.."              
[76] "fBodyAcc.std...X"                     "fBodyAcc.std...Y"                     "fBodyAcc.std...Z"                    
[79] "fBodyAccJerk.std...X"                 "fBodyAccJerk.std...Y"                 "fBodyAccJerk.std...Z"                
[82] "fBodyGyro.std...X"                    "fBodyGyro.std...Y"                    "fBodyGyro.std...Z"                   
[85] "fBodyAccMag.std.."                    "fBodyBodyAccJerkMag.std.."            "fBodyBodyGyroMag.std.."              
[88] "fBodyBodyGyroJerkMag.std.."



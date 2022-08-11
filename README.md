# School_District_Analysis
Intriduction to Pandas, using Anaconda, Jupyter Notebook as well

# Overview 
## Project Overview
Python can be used to pull data from one place and save it in another, as well as automate a wide variety of tasks. With Pandas, Python becomes a powerful data analysis tool in its own right and can transform and validate data, perform sophisticated data analysis, and even create data visualizations.

## Purpose of the School District Analysis
The purpose of this project is to conduct a school district analysis using Anaconda &amp; Jupyter Notebook. The data we are analyzing comes from two sources: one is a csv containing school data and another is a csv containing data on the students from those schools. The school data file contains information related to the school name, the type of school (whether Charter or District), the size of the school, and the budget of the school. The data on the students contains information such as their name, school, grade, and individual scores on math and reading. The common data between these two files is the "School Name" column. In this analysis we will load our data from the two csv's into dataframes to better visualize the data and sort and group the data, then we will merge the two datasets into one dataframe to find trends, view summaries, and sort by overall performance, math and reading scores, and school spending. We will also address an issue that was brought to light by the school board wherein there is evidence of academic dishonesty; specifically, that reading and math grades for Thomas High School ninth graders appear to have been altered. Therefore we will also clean the data and disregard those grades from Thomas High School ninth graders before conducting the final analysis. 

# Results
## How is the district summary affected?
The district summary is actually not affected much by the changes of replacing 9th grade Thomas High School Student Data with Nan because the District Summary DataFrame is not analyzing only data per student, but also analyzing data by overall school information such as total schools, total students, and total budget. The numbers that look at Average Scores, Passing Scores, and Overall Passing Scores are only slightly different in total. The very slight change that is a slight decrease in overall passing and average scores is likely due to the fact that when we exclude the data that was falsified (9th graders from Thomas High School), the average passing scores go down a little. These changes between the original and updated summary can be found below. 
### Code to replace 9th grade with NaN
![replace](https://user-images.githubusercontent.com/73972332/102053799-2b447a80-3d9d-11eb-8afd-2bc4a907fd7d.png)
### Original District Summary
![DS Original](https://user-images.githubusercontent.com/73972332/102035199-a9d8f200-3d74-11eb-8d20-82d0dbb06cc6.png)
### Refactored District Summary
![DS Updated](https://user-images.githubusercontent.com/73972332/102041632-d09f2480-3d84-11eb-88d3-dc60716dbb1c.png)
## How is the school summary affected?
The school summary dataframe is affected in that after removing the false/altered data from the calculations, the scores drop overall for Thomas High School. When the falsified data was included, the scores were much higher for the percentage of those passing math, reading, and overall. When the data is excluded, the passing scores drop from the mid 90's to the mid 60's. This makes sense, given that the falsified/innacurate data would reflect a higher score overall and that the general scores would drop when the data is not counted. See the differences below in the two graphs (one for the original, and one that is filtered). This data is different because we have replaced the 9th grade reading and math scores at Thomas High School with NaN in the beginning of this analysis. 
### Original Per School Summary
![Per School Summary Original](https://user-images.githubusercontent.com/73972332/102043045-45279280-3d88-11eb-9e88-dcac11df71f9.png)
### Refactored Per School Summary
![Per School Summary Updated](https://user-images.githubusercontent.com/73972332/102043065-4f499100-3d88-11eb-9c9f-46e6e04694f4.png)
## How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
Replacing the ninth graders' math and reading scores with Nan values clearly affects Thomas High School's performance relative to the other schools by showing that Thoma High School's freshmen are relatively struggling. The scores drop clearly when the innacurate data is excluded. For example, in the original code, when we sorted by top 5 schools, Thomas High School actually came in rated second. However, when substituting Nan for the inaccurate values, Thomas High School's % overall passing drops down around 65%, bringing it's standing compared to the other schools, much lower. 
### Original Top Performing Schools
![sorted top 5 1](https://user-images.githubusercontent.com/73972332/102043729-0eeb1280-3d8a-11eb-9001-1564e215eba2.png)
### Thomas High School's % Passing after Excluding False Data
![Per School Summary Updated 3](https://user-images.githubusercontent.com/73972332/102043918-959fef80-3d8a-11eb-96d1-798c05ade94c.png)
## How does replacing the ninth-grade scores affect the following: 
### Math and reading scores by grade
Replacing the ninth-graders scores affects the math and reading scores by grade simply by excluding the data for that column for that specific grade and that specific school. The data simply becomes Nan or null. All other data is left untouched for the other schools. Only Thomas High School is affected in the data that shows scores by grade. See images below. 
#### Math Original vs Updated
![Math Grade Original](https://user-images.githubusercontent.com/73972332/102044478-ba489700-3d8b-11eb-869f-647a45655e86.png)
![Math Grade Updated](https://user-images.githubusercontent.com/73972332/102044499-c2a0d200-3d8b-11eb-97dd-79cd75afb58f.png)
#### Reading Original vs Updated
![reading grade original](https://user-images.githubusercontent.com/73972332/102044509-c9c7e000-3d8b-11eb-9f53-e281e0c02bc0.png)
![Reading Grade Updated](https://user-images.githubusercontent.com/73972332/102044523-d0565780-3d8b-11eb-967a-6c3fbf46ca2b.png)
### Scores by school spending
Replacing the ninth-graders scores does not actually affect the scores by schools spending because by the time we run this code, we will have replaced the overall Thomas High School passing scores in the dataframe with data for only the 10th through 12th grade and will not even count the ninth graders data in this analysis. So the scores by school spending dataframe remains unchanged. If we had caclulated this data before updating the frame to only show for 10th through 12th, the school spend per student would be much higher. I noticed in this code, that our challenge didn't ask us to update the dataframe for total students at Thomas High School to show as only 1,173 (1635 - 461 ninth graders). If the code had asked us to update our dataframe for total students from Thomas High School to be only 1,173 (10th Grade to 12th Grade Only), then the total spend per student would be much higher at $889.28 and would bump this school way up on the spending range per student. 
#### Scores by School Spending Original
![Schools Spending Original](https://user-images.githubusercontent.com/73972332/102049698-3cd65400-3d96-11eb-8211-159624bfd1c3.png)
#### Scores by School Spending Updated
![Schools Spending Updated](https://user-images.githubusercontent.com/73972332/102049718-43fd6200-3d96-11eb-932d-8c74eda1347d.png)
### Scores by school size
When we view the dataframes for scores by school size, we encounter the same phenomenon as we did in the last section (scores by spending), in that the data remains relatively unchanged from the first dataframe to the second, because we eliminated the ninth grader information from the average and passing scores, but the challenge code never asked us to update the total student number. For this reason, and because the 10th-12th graders had relatively the same scores as was counted in the original code with the inaccurate data of the 9th graders, we can see that there is really no difference of output below. Also the school size (even if we subtract the amount of 9th grader students), remains in the Medium Range(1,000 - 2,000). 
#### Scores by School Size Original
![scores school size original](https://user-images.githubusercontent.com/73972332/102049992-cede5c80-3d96-11eb-8452-a102a78a50a2.png)
#### Scores by School Size Updated
![scores school size updated](https://user-images.githubusercontent.com/73972332/102050008-d56cd400-3d96-11eb-86f3-ae2e1000c152.png)
### Scores by school type
In this next section, we again see the same type of outcome that we saw in the previous two sections. The data remains unchanged in the scores by school type because again, we have eliminated the 9th grade null data, and replaced our datasets with only the passing grade info from 10th to 12th grade. If we left the dataset as affected by the null values, we would see a change in the scores, however at the end of the challenge code, we replaced this lower data, with info that shows just from the 10th-12th grades, which bring our scores back to the same as they were originally. 

![scores school type updated](https://user-images.githubusercontent.com/73972332/102050805-51b3e700-3d98-11eb-8f80-a07f22f29640.png)
# Summary
## Summary of 4 Major Changes in Updated DataFrame
Major changes to the school district analysis after reading and math scores have been replaced are: 
  1) The first replacement of the 9th grade values with Nan bring down all the scores from Thomas High School across the board. But then, at the end of our code, we replace the      school summary code with code that only counts the 10th-12th grade passing data. This brings our data back up. In our final dataframe therefore: 
  2) the grades % increased for Thomas High School so it went from a low performing to a high performing school
  3) the % Passing Math Scores for Thomas High School returned back up to 93 from 66.9 
  4) the % Passing Reading returned back up to 97 from 69.6 
  5) the overall percentage of the passing returned back up to 90 from 65. 
#### Code where we replace DataFrame with values for only 10th-12th. 
![final replace](https://user-images.githubusercontent.com/73972332/102053894-575ffb80-3d9d-11eb-87f1-4ff15fa4a323.png)
#### Before replacing the math & reading scores
![Per School Summary Updated 2](https://user-images.githubusercontent.com/73972332/102052895-b886cf80-3d9b-11eb-973f-9d447b3749b8.png)
#### After replacing the math & reading scores
![Replacing math reading](https://user-images.githubusercontent.com/73972332/102053149-1b786680-3d9c-11eb-8c94-b41e1cda0c6a.png)

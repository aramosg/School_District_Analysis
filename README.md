# Module 4 – PyCitySchools with Pandas [School District Analysis]
# Unit Challenge

## Overview of the school district analysis
We have being asked to perform data analysis on a given data set, containing data from different school. The main purpose of analyzing this data is to detect trends in school performance. The analysis we deliver well support the School Board in making decisions about budget and priorities. 

After delivering the initial analysis, we have been informed about the suspicion of academic dishonesty, specifically for the 9th grade in the Thomas High School scores. We will be removing these grades and do the analysis again. We will discover how these changes affect the results of the analysis. 

## Results of the analysis
### 1. How is the district summary affected?
This is a snapshot showing he district analysis before removing the reading and math scores from Thomas High School 9th graders:
![District summary with Thomas High Schools 9th graders](/resources/01_before_district_summary.png)

and after the removal of the Thomas High School 9th graders grades:
![District summary with no Thomas High Schools 9th graders](/resources/01_after_district_summary.png)

As we can see, the only metric which remain the same is the **average reading score**. All other metrics are reporting a slight decrease. 

### 2. How is the school summary affected?
This is a snapshot showing the school summary before removing the reading and math scores from Thomas High School 9th graders:
![School summary with Thomas High Schools 9th graders](/resources/02_before_school_summary.png)

and after the removal of the Thomas High School 9th graders:
![District summary with no Thomas High Schools 9th graders](/resources/02_after_school_summary.png)

In this analysis (school summary), we see some significant changes. The average math and reading scores are slightly changing, but nothing dramatic. Generaly speaking, you can barely see the differences. It is a different story with the passing percentages for Thomas High School. The passing percentages for reading, math, and overall are observing a dramatic drop.

### 3. How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
As highlighted in the previous question, the average scores for reading and math remain almost the same:
- Average math score: 83.41 vs 83.35 (slight decrease)
- Average reading score: 83.84 vs 83.89 (slight increase)

For the percentage, the story goes the opposite direction. Variations are dramatic:
- Percentage passing math: 93.27 vs 66.91 (dramatic decrease)
- Percentage passing reading: 97.30 vs 69.66 (dramatic decrease)
- Overall passing percentage: 90.94 vs 65.07 (dramatic decrease)

My theory for this big change is the way we are calculating the mean versus how we are calculating the percentages. For the mean, we are using the pandas MEAN method, which automatically ignore the "NaNs" by default. To calculate the percentages, we are considering a student count of 39170. This number includes Thomas High School (THS) 9th grades. Since this students do not have grades, this has a big impact in the calculations.  

### 4. How does replacing the ninth-grade scores affect the following:
#### 4.1 Math and reading scores by grade
The math and reading scores for the whole set of data was unchanged. We are segregating by grade, so the expected result is to see a change in the 9th grade notes only. As you can see in the images below, we can confirm our hipotheis. We can see a "NaN" for Thomas High School 9th grade. The rest of the grades remain the same.

Showing the math and reading scores by grade **before** replacing the 9th graders notes with NaN:

Math scores by grade

![Before - Math scores by grade](/resources/04_01_before_math_by_grade.png)

Reading scores by grade

![Before - Reading scores by grade](/resources/04_01_before_reading_by_grade.png)

Now showing the scores **after** replacing the 9th graders notes witn NaN:

Math scores by grade

![After - Math scores by grade](/resources/04_01_after_math_by_grade.png)

Reading scores by grade

![After - Reading scores by grade](/resources/04_01_after_reading_by_grade.png)

#### 4.2 Scores by school spending
The scores are exactly same before and after the replacement of the Thomas High School 9th grades notes. See the images below:

Before replacing the 9th grades with NaN

![Before - Scores by school spending](/resources/04_02_before_spending_summary.png)

After replacing the 9th grades with NaN

![After - Scores by school spending](/resources/04_02_after_spending_summary.png)


#### Scores by school size
#### Scores by school type

## Summary
Summarize four changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.

# project-Python-04-A-B-testing

__Case-01.__ More 'Click-Through-Rate' in the new website ? Does the experiment webpage drive higher traffic than the control webpage ? 
 - package: Pandas, Numpy, Matplotlib, Seaborn 
 - func:

__Case-02.__ More Career focused description of the online-course lead more success for both the website and the student-customers ?
 - package: Pandas, Numpy, Matplotlib, Seaborn 
 - func:

__Case-03.__ 
 - package: 
 - func: 
-------------------------------------------------------------------------------------------------------------------------------------  
# [Case I]. Does the 'experiment' webpage drive higher traffic than the 'control' webpage ? Which one is better ? 

__Data:__ 
 - timestamp
 - id
 - group: control / experiment
 - action: view / click
<img src="https://user-images.githubusercontent.com/31917400/34457310-a8536276-eda4-11e7-956e-13b52bb8e6ea.jpg" width="700" height="180" />

 - number of unique users - 6328
```
df['id'].nunique()
```
 - size of control group and experiment group - (3332, 2996)
```
df.query('group == "control"').id.nunique(), df.query('group == "experiment"').id.nunique() 
```
 - action types in this experiment
``` 
df.action.unique()
```
 - duration of this experiment - ('2016-09-24 17:42:27.839496', '2017-01-18 10:24:08.629327')
``` 
df.timestamp.min(), df.timestamp.max()
```

__Story:__
 - Definition of click through rate (CTR) for this experiment
   - The No.of unique visitors who click at least once / The No.of unique visitors who view the page 
 - Why would we use 'Click-Through-Rate' instead of number of clicks to compare the performances of control and experiment pages? Because... Getting the proportion of the users who click is more effective than getting the number of users who click when comparing groups of different sizes. ie..more total clicks could occur in one version, even if there is a greater percentage of clicks in the other version (simpson's paradox).
 - Steps to analyze the results of this A/B test.
   - 1. We computed the observed difference between the metric, click through rate, for the control and experiment group.
   - 2. We simulated the sampling distribution for the difference in proportions (or difference in click through rates).
   - 3. We used this sampling distribution to simulate the distribution under the null hypothesis, by creating a random normal distribution centered at 0 with the same spread and size.
   - 4. We computed the p-value by finding the proportion of values in the null distribution that were greater than our observed difference.
   - 5. We used this p-value to determine the statistical significance of our observed difference.

<img src="https://user-images.githubusercontent.com/31917400/34457350-2dadfb60-eda6-11e7-9a81-c1d784ad2263.jpg" />

































# Practical-Application-Mod-5
The project/repo contains the following files
# 1. coupons.csv: 
A CSV named coupons.csv which has details of  different coupons offered to drivers, their predicament at the time coupon was offered and the fact whather the coupon was offered or discarded

# 2. prompt.ipynb: 
A jupyter notebook that summarizes the observations/inferences from CSV on the different trends for acceptance of Bar and Coffee Coupons and answering some of the questions that were asked in the assignment    
## 2.1 Describe DataFrame
       Leveraging the describe method one can get the mean, standard deviations, count for different numerical columns that comprise the data set. Most of the numerical columns are logical booleans which could well have been True or False values. E.g: has_children
![image](https://github.com/user-attachments/assets/cae7d57d-5499-43bf-8490-02f6571394a8)

## 2.2 DataFrame Information
       By running the info() method one can infer that there are ton of notional string and numerical values which have been represented as objects. e.g.: Destination, passangar and weather all could be string columns. In a similar vein 'Income' could be a float value
![image](https://github.com/user-attachments/assets/daa8a185-f75e-4da6-bb49-777cfd53583c)

## 2.3 Null Check
       Observed that the column 'car' has 12576 null values , where as columns Bar, CoffeeHouse, CarryAway, rRestaurantLessThan20, 20to50 have a null values for around 100-150 columns. The car column is not very useful as majority of the rows have this column value as NULL
![image](https://github.com/user-attachments/assets/1714abc8-0303-42e9-913f-b7dc796ba4b9)
## 2.4 Handle Nulls
### 2.4.1 Drop Redundant Columns
       Drop columns like 'car' which has majority null rows and is not very useful as it stands
![image](https://github.com/user-attachments/assets/baf59baa-97a5-4855-aaa4-75c16a86f3fd)

### 2.4.2 Replace Null Values       
       For the rest of the columns which have few null values, fill the null columns with the most frequently occuring value for that column using value_count() and idxmax() functions in conjunction. Validate that the isna().sum() returns 0 for all the columns after this exercise   Write the cleansed rows into a new data frame data_cleansed
![image](https://github.com/user-attachments/assets/8467a435-8384-4988-ae1a-a2d37782db1d)


## 2.5  Unify Unit Of Measure for the column expiration
 The unit of measure mentioned for expiration has different Unit of Measure like 'd'( day) and 'h'( hour) . leveraging the knowledge we are better of converting the same to one common Unit of Measure. Doing this for potential usage later. Defined a function **convertToCommonUOM** to convert into the common unit of measure hours and persist the same in a different column in the **data_cleansed** dataframe
 
 ![image](https://github.com/user-attachments/assets/eaccb3c3-b0d1-47dc-b80c-5c58770b9c18)

 ## 2.6 Answer to the Question "**4. What proportion of the total observations chose to accept the coupon?**"
 Observed that around 56.84 percentage of coupons were accepted across coupon groups
 ![image](https://github.com/user-attachments/assets/0a335db4-fe31-4a90-84f2-34881d2d2d01)

 ## 2.7 Answer to the instruction "5. Use a bar plot to visualize the `coupon` column."
 Observation: CoffeHouse copuns and Cheaper restaurants are the coupon groups against which maximum coupons have been offered .The high end restaurants coupon group has the least coupons offered ( as per the sample dataset shared)
 ![image](https://github.com/user-attachments/assets/c2d29ca3-3b3b-4593-8425-a5b6e59c04f8)

 ## 2.8 Answer to the Instruction "Use a histogram to visualize the temperature column."
Observation: There are just 3 values for temperature in the observation data set and it does not follow a normal distribution
![image](https://github.com/user-attachments/assets/027ae8ec-9ebc-40c1-a8a7-dc5b5c98e77c)

## 2.9 Investing Bar Coupons
### 2.9.1: Create a new DataFrame that contains just the bar coupons.
Observation: The bar coupons account for 2017 records in a set of 12684 observations in the coupons.csv
![image](https://github.com/user-attachments/assets/8c22326d-42e8-4efc-87f7-6584fecbef19)

### 2.9.2: Answer to the question : What proportion of bar coupons were accepted?
Answer: Approximately 41 % of the bar coupons are accepted 
![image](https://github.com/user-attachments/assets/61c4c7e1-7b52-4834-9345-62824af1da67)

### 2.9.3: Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.
   
       1. Acceptance rate of bar coupons by those who frequented the bars 3 times or fewer in a month:0.**37073707370737075**
       2.Acceptance rate of bar coupons by those who frequented the bars more than 3 times in a month 0.**7688442211055276**
       3. The acceptance ratio for bar coupons by those who frequented bar more than 3 times a month is ~double the number of acceptances from those who did not frequent the bar as much, and is much higher than the acceptance rate of the whole sample set ( which stands at ~41 percent)
       
![image](https://github.com/user-attachments/assets/2035a940-5ba2-433a-9f27-481e83a6839a)

### 2.9.4: Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to the all others.  Is there a difference?
Coupon acceptance rate of the drivers who frequent the bar more than once a month and are over 25 years of age.**6952380952380952**
The number of drivers who are over 25 and frequent the bar over once a month are ~ twice as likely to accept a bar coupon , with respect to the rest of the cohort who have been offered bar coupon. The acceptance rate for this cohort is also much higher than the rate of acceptance of bar coupons for the whole sample set ( which stands at ~41$)

![image](https://github.com/user-attachments/assets/b4ce2e9c-1e3b-4b7a-bc5d-702e3e130676)

### 2.9.5: Use the same process to compare the acceptance rate between drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry.

       Observation: Acceptance ratio for cohort who frequent the bar over a month, travelling without kids and not working in farming,fishing or forestry: 0.7132486388384754
       Over 70% of the cohort who frequent bars more than once a month, travelling without kids and having an occupation that is not farming, fishing or forestry accept a Bar Coupon when they are offered the same . This is much higher than the rest of the cohorts who have around 29% acceptance
![image](https://github.com/user-attachments/assets/6533e7f7-26a7-4c90-9cc0-d793b6e89bed)

### 2.9.6: Compare the acceptance rates between those drivers who:
**condition 1**:go to bars more than once a month, had passengers that were not a kid, and were not widowed OR
**condition 2**:go to bars more than once a month and are under the age of 30 OR
**condition 3**:go to cheap restaurants more than 4 times a month and income is less than 50K.

**Observation/Statistics**: 
1. The ratio of acceptance with either of the Conditions are met( OR) 0.5889175257731959
2.The ratio of acceptance with only first condition satisfied 0.7132486388384754
3.The ratio of acceptance with only second condition satisfied 0.7217391304347827
4. The ratio of acceptance with only third condition satisfied 0.45348837209302323

**Inference**
The 3 conditions in isolation shows that
1. Drivers who did not drive kids around , were not widowed and visited bar more than once in a month had 71% plus acceptance rates.
2. Drivers who frequent bars more than once in a month and are under the age of 30 have 72% acceptance rates
3. Drivers who went to cheap restaurants more than 4 times a month and whose income level was below 50K had only 45% acceptance rates
4. ALl this conditions joined by an OR was 58% acceptance rates

Younger drivers( below 30) who frequent bars more than once a month and do not drive kids have higher acceptance rates of bar coupons. People who visit cheap restaurants more than 4 times a month and who earn south of 50K did not show the same acceptance rates as the other cohorts

![image](https://github.com/user-attachments/assets/160e9114-72cc-44d5-a808-6b4e3570b8fa)

### 2.9.7: Based on these observations, what do you hypothesize about drivers who accepted the bar coupons?
**Observations** from the plots and other assignment question¶
1. Drivers age, frequency of visits to the bar, the fact whether they were driving a passanger who was a kid , income level has a strong bearing on the fact if the given coupon would be accepted
2. From the initial look people tend to accept the bar coupon when travelling with their friends and the least when they are travelling with their kids, but the black bar also denotes the variability of data in each group
3. At the occupation category, the folks in 'Education&Training&Library' and "Retired" category showed lesser affinity to actually accept the coupon
4. No striking trend wrt acceptance when looking at the influence of income in isolation
5. Rich singles with 100K plus income have a higher percentage of acceptance of bar coupons
6. Singles genrally have a higher acceptance rates for bar coupons
7. The evening and later in the night are when the bar coupons have higher acceptance rates

![image](https://github.com/user-attachments/assets/bbcbfb79-a430-4a99-b718-d7cac8a863b9)

![image](https://github.com/user-attachments/assets/22d9c45f-4ad8-4dea-9c7e-3815b816cc9f)

![image](https://github.com/user-attachments/assets/d866373b-58c8-4a33-84a3-1390ff54b344)

# 2.10:Independent Investigation
Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons.  Let us dwell deeper into coupon group "CoffeeHouse" as that seems to have higher volume of data. Around 3996 rows make it to the selection

## 2.10.1: Influence of time of the day on Coffee Coupon Acceptance
**Observation**
Higher acceptance of Coffee Coupons at 10 AM timeslot, irrespective of the expiration timeframe of the coupon
Coupons which has an expiration lasting a day and are offered at 10 PM , have higher rate of acceptance when offered in the 10 PM slot, inspite of generally low acceptance otherwise( for the same timeslot)

![image](https://github.com/user-attachments/assets/11c869ba-7a3c-416b-8866-63a17bb666ae)

## 2.10.2: Influence of destination on Coffee Coupon Acceptance
**Observation**
No catchy patterns emerge when we look at the Bar Plots for Coupon Acceptance for Coffee for categorical columns destination, marital status and income. Although a pattern emerges that the passangers have a greater rate of acceptance for coffee coupons when they are not travelling to either home or office and the travel is non-urgent

![image](https://github.com/user-attachments/assets/1dcc1408-c7d0-4037-8881-540ee1686dcd)

![image](https://github.com/user-attachments/assets/9ddfe41c-95f0-461e-b72c-5ec85b9578d9)

## 2.10.3: Other Observations
Coffee acceptance number is higher
1. When one is travelling to 'No Urgent Place', at 10 AM
2. Among ages 21 and 26 age group
3. Visit the coffee shop 1-3 times a month
4. Students have higher acceptance rate

# 3. images folder
A folder that is home to different plots generated as a part of analysis in prompt.ipynb. Includes bar charts and histograms comparing different categorical attributes and the trends on coupon acceptance

# Practical-Application-Mod-5
The project/repo contains the following files
# 1. coupons.csv: A CSV named coupons.csv which has details of  different coupons offered to drivers, their predicament at the time coupon was offered and the fact whather the coupon was offered or discarded
# 2. prompt.ipynb: A jupyter notebook that summarizes the observations/inferences from CSV on the different trends for acceptance of Bar and Coffee Coupons and answering some of the questions that were asked in the assignment    
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
       For the rest of the columns which have few null values, fill the null columns with the most frequently occuring value for that column using value_count() and idxmax() functions in conjunction. Validate that the isna().sum() returns 0 for all the columns after this exercise   
       ![image](https://github.com/user-attachments/assets/540173df-3f45-4d9a-9569-6ecf782c7230)
       ![image](https://github.com/user-attachments/assets/0dedca7e-a733-441b-ac10-75777714ac4a)



# 3. images folder: A folder that is home to different plots generated as a part of analysis in prompt.ipynb. Includes bar charts and histograms comparing different categorical attributes and the trends on coupon acceptance

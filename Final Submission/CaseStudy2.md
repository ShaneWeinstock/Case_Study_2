---
title: "CaseStudy2"
author: "Kari Theobald, Shane Weinstock, Jeremy Simpson, Gabe Gonzales"
date: "4/3/2019"
output:
  html_document:
    keep_md: yes

---
# EXECUTIVE SUMMARY
DDSAnalytics provided employee profiles on the current workforce of ChemicalRepo. We were requested to review the data to discover the three most contributing reasons of attrition at ChemicalRepo. As Data Scientists, we have a request from DDSAnalytics management to determine other interesting facts within this data on ChemicalRepo. We tested several variables and believed that the greatest contributing factors to attrition were the age of employment and those within the sales representative department. While we discovered these factors, we found that there were several other interesting variables within the data and proceeded to analyze them as well. We have prepared several graphical representations and correlations that help illustrate the factors we've been able to illuminate with this data. This illumination can be found in this report along with several written conclusions to help provide the least amount of attrition and the greatest amount of variation for ChemicalRepo moving forward. 

# HYPOTHESIS
We hypothesize, the sales departments, age and overall commute distance contributes to attrition within a company. 

# INTRODUCTION
DDSAnalytics a Fortune 1000 Company, is requesting their Data Scientist to review the data provided by ChemicalRepo. The management at DDSAnalytics instructs to the Data Scientist, all results from the data must carry the exclusion of all employees under the age of 18. DDSAnalytics also request three factors associated to attrition in ChemicalRepo.  DDSAnalytics would like to suggest to ChemicalRepo workforce planning and identify high-potential employees who attribute to turnover. The management in DDSAnalytics will be using this data research as leverage in their talent management business. The Data Scientist will meet the request of reviewing attrition, they will also examine specific job role trends and report the findings. 



```r
#install.packages("readxl")
#install.packages("ggplot2")
#install.packages("dataMaid")

library(readxl)
library(plyr)
library(ggplot2)
library(plyr)
library(dataMaid)
```

```
## 
## Attaching package: 'dataMaid'
```

```
## The following object is masked from 'package:plyr':
## 
##     summarize
```

```r
#Establish the working directory.
getwd()
```

```
## [1] "/Users/ktheobald/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2/Working Folder"
```

### 2.a ) Read the CSV file (we have xlsx) into the dataset call it Data. Output how many rows and columns 


```r
New.Data <- read_xlsx("CaseStudy2-data.xlsx")
```

```
## readxl works best with a newer version of the tibble package.
## You currently have tibble v1.4.2.
## Falling back to column name repair from tibble <= v1.4.2.
## Message displays once per session.
```

```r
Data <- data.frame(New.Data)
head(Data) # original import of all data 
```

```
##   Age Attrition    BusinessTravel DailyRate             Department
## 1  41       Yes     Travel_Rarely      1102                  Sales
## 2  49        No Travel_Frequently       279 Research & Development
## 3  37       Yes     Travel_Rarely      1373 Research & Development
## 4  33        No Travel_Frequently      1392 Research & Development
## 5  27        No     Travel_Rarely       591 Research & Development
## 6  32        No Travel_Frequently      1005 Research & Development
##   DistanceFromHome Education EducationField EmployeeCount EmployeeNumber
## 1                1         2  Life Sciences             1              1
## 2                8         1  Life Sciences             1              2
## 3                2         2          Other             1              4
## 4                3         4  Life Sciences             1              5
## 5                2         1        Medical             1              7
## 6                2         2  Life Sciences             1              8
##   EnvironmentSatisfaction Gender HourlyRate JobInvolvement JobLevel
## 1                       2 Female         94              3        2
## 2                       3   Male         61              2        2
## 3                       4   Male         92              2        1
## 4                       4 Female         56              3        1
## 5                       1   Male         40              3        1
## 6                       4   Male         79              3        1
##                 JobRole JobSatisfaction MaritalStatus MonthlyIncome
## 1       Sales Executive               4        Single          5993
## 2    Research Scientist               2       Married          5130
## 3 Laboratory Technician               3        Single          2090
## 4    Research Scientist               3       Married          2909
## 5 Laboratory Technician               2       Married          3468
## 6 Laboratory Technician               4        Single          3068
##   MonthlyRate NumCompaniesWorked Over18 OverTime PercentSalaryHike
## 1       19479                  8      Y      Yes                11
## 2       24907                  1      Y       No                23
## 3        2396                  6      Y      Yes                15
## 4       23159                  1      Y      Yes                11
## 5       16632                  9      Y       No                12
## 6       11864                  0      Y       No                13
##   PerformanceRating RelationshipSatisfaction StandardHours
## 1                 3                        1            80
## 2                 4                        4            80
## 3                 3                        2            80
## 4                 3                        3            80
## 5                 3                        4            80
## 6                 3                        3            80
##   StockOptionLevel TotalWorkingYears TrainingTimesLastYear WorkLifeBalance
## 1                0                 8                     0               1
## 2                1                10                     3               3
## 3                0                 7                     3               3
## 4                0                 8                     3               3
## 5                1                 6                     3               3
## 6                0                 8                     2               2
##   YearsAtCompany YearsInCurrentRole YearsSinceLastPromotion
## 1              6                  4                       0
## 2             10                  7                       1
## 3              0                  0                       0
## 4              8                  7                       3
## 5              2                  2                       2
## 6              7                  7                       3
##   YearsWithCurrManager
## 1                    5
## 2                    7
## 3                    0
## 4                    0
## 5                    2
## 6                    6
```

```r
dim(Data) # how many rows and columns in the original data set. 
```

```
## [1] 1470   35
```

### 2.b ) Change col names to less than 12 characters in the  dataframe.

```r
names <- c( "Age", "Attrition", "Feq.Travel", "Daily.Rate", "Department", "mlg.Home", "Education", "Ed.Field", "Emp.Count", "Emp.Number", "Env.Sat", "Gender", "HourlyRate", "Job.Invol", "Job.Level", "Title", "Satisfied", "M.S.D", "Income.mos","Rate.mos", "Jobs.Worked", "Over18", "OT", "Percent.Inc" , "Performance", "Sat.Relation", "Hours", "Stock", "Yrs.Wrkd", "Training", "Work.Life", "YOS", "YCRole","YbtwnPromo", "YwMgmt")

Data <- setNames(Data, names)

#check new names
head(Data)  
```

```
##   Age Attrition        Feq.Travel Daily.Rate             Department
## 1  41       Yes     Travel_Rarely       1102                  Sales
## 2  49        No Travel_Frequently        279 Research & Development
## 3  37       Yes     Travel_Rarely       1373 Research & Development
## 4  33        No Travel_Frequently       1392 Research & Development
## 5  27        No     Travel_Rarely        591 Research & Development
## 6  32        No Travel_Frequently       1005 Research & Development
##   mlg.Home Education      Ed.Field Emp.Count Emp.Number Env.Sat Gender
## 1        1         2 Life Sciences         1          1       2 Female
## 2        8         1 Life Sciences         1          2       3   Male
## 3        2         2         Other         1          4       4   Male
## 4        3         4 Life Sciences         1          5       4 Female
## 5        2         1       Medical         1          7       1   Male
## 6        2         2 Life Sciences         1          8       4   Male
##   HourlyRate Job.Invol Job.Level                 Title Satisfied   M.S.D
## 1         94         3         2       Sales Executive         4  Single
## 2         61         2         2    Research Scientist         2 Married
## 3         92         2         1 Laboratory Technician         3  Single
## 4         56         3         1    Research Scientist         3 Married
## 5         40         3         1 Laboratory Technician         2 Married
## 6         79         3         1 Laboratory Technician         4  Single
##   Income.mos Rate.mos Jobs.Worked Over18  OT Percent.Inc Performance
## 1       5993    19479           8      Y Yes          11           3
## 2       5130    24907           1      Y  No          23           4
## 3       2090     2396           6      Y Yes          15           3
## 4       2909    23159           1      Y Yes          11           3
## 5       3468    16632           9      Y  No          12           3
## 6       3068    11864           0      Y  No          13           3
##   Sat.Relation Hours Stock Yrs.Wrkd Training Work.Life YOS YCRole
## 1            1    80     0        8        0         1   6      4
## 2            4    80     1       10        3         3  10      7
## 3            2    80     0        7        3         3   0      0
## 4            3    80     0        8        3         3   8      7
## 5            4    80     1        6        3         3   2      2
## 6            3    80     0        8        2         2   7      7
##   YbtwnPromo YwMgmt
## 1          0      5
## 2          1      7
## 3          0      0
## 4          3      0
## 5          2      2
## 6          3      6
```

```r
summary(Data)
```

```
##       Age         Attrition          Feq.Travel          Daily.Rate    
##  Min.   :18.00   Length:1470        Length:1470        Min.   : 102.0  
##  1st Qu.:30.00   Class :character   Class :character   1st Qu.: 465.0  
##  Median :36.00   Mode  :character   Mode  :character   Median : 802.0  
##  Mean   :36.92                                         Mean   : 802.5  
##  3rd Qu.:43.00                                         3rd Qu.:1157.0  
##  Max.   :60.00                                         Max.   :1499.0  
##   Department           mlg.Home        Education       Ed.Field        
##  Length:1470        Min.   : 1.000   Min.   :1.000   Length:1470       
##  Class :character   1st Qu.: 2.000   1st Qu.:2.000   Class :character  
##  Mode  :character   Median : 7.000   Median :3.000   Mode  :character  
##                     Mean   : 9.193   Mean   :2.913                     
##                     3rd Qu.:14.000   3rd Qu.:4.000                     
##                     Max.   :29.000   Max.   :5.000                     
##    Emp.Count   Emp.Number        Env.Sat         Gender         
##  Min.   :1   Min.   :   1.0   Min.   :1.000   Length:1470       
##  1st Qu.:1   1st Qu.: 491.2   1st Qu.:2.000   Class :character  
##  Median :1   Median :1020.5   Median :3.000   Mode  :character  
##  Mean   :1   Mean   :1024.9   Mean   :2.722                     
##  3rd Qu.:1   3rd Qu.:1555.8   3rd Qu.:4.000                     
##  Max.   :1   Max.   :2068.0   Max.   :4.000                     
##    HourlyRate       Job.Invol      Job.Level        Title          
##  Min.   : 30.00   Min.   :1.00   Min.   :1.000   Length:1470       
##  1st Qu.: 48.00   1st Qu.:2.00   1st Qu.:1.000   Class :character  
##  Median : 66.00   Median :3.00   Median :2.000   Mode  :character  
##  Mean   : 65.89   Mean   :2.73   Mean   :2.064                     
##  3rd Qu.: 83.75   3rd Qu.:3.00   3rd Qu.:3.000                     
##  Max.   :100.00   Max.   :4.00   Max.   :5.000                     
##    Satisfied        M.S.D             Income.mos       Rate.mos    
##  Min.   :1.000   Length:1470        Min.   : 1009   Min.   : 2094  
##  1st Qu.:2.000   Class :character   1st Qu.: 2911   1st Qu.: 8047  
##  Median :3.000   Mode  :character   Median : 4919   Median :14236  
##  Mean   :2.729                      Mean   : 6503   Mean   :14313  
##  3rd Qu.:4.000                      3rd Qu.: 8379   3rd Qu.:20462  
##  Max.   :4.000                      Max.   :19999   Max.   :26999  
##   Jobs.Worked       Over18               OT             Percent.Inc   
##  Min.   :0.000   Length:1470        Length:1470        Min.   :11.00  
##  1st Qu.:1.000   Class :character   Class :character   1st Qu.:12.00  
##  Median :2.000   Mode  :character   Mode  :character   Median :14.00  
##  Mean   :2.693                                         Mean   :15.21  
##  3rd Qu.:4.000                                         3rd Qu.:18.00  
##  Max.   :9.000                                         Max.   :25.00  
##   Performance     Sat.Relation       Hours        Stock       
##  Min.   :3.000   Min.   :1.000   Min.   :80   Min.   :0.0000  
##  1st Qu.:3.000   1st Qu.:2.000   1st Qu.:80   1st Qu.:0.0000  
##  Median :3.000   Median :3.000   Median :80   Median :1.0000  
##  Mean   :3.154   Mean   :2.712   Mean   :80   Mean   :0.7939  
##  3rd Qu.:3.000   3rd Qu.:4.000   3rd Qu.:80   3rd Qu.:1.0000  
##  Max.   :4.000   Max.   :4.000   Max.   :80   Max.   :3.0000  
##     Yrs.Wrkd        Training       Work.Life          YOS        
##  Min.   : 0.00   Min.   :0.000   Min.   :1.000   Min.   : 0.000  
##  1st Qu.: 6.00   1st Qu.:2.000   1st Qu.:2.000   1st Qu.: 3.000  
##  Median :10.00   Median :3.000   Median :3.000   Median : 5.000  
##  Mean   :11.28   Mean   :2.799   Mean   :2.761   Mean   : 7.008  
##  3rd Qu.:15.00   3rd Qu.:3.000   3rd Qu.:3.000   3rd Qu.: 9.000  
##  Max.   :40.00   Max.   :6.000   Max.   :4.000   Max.   :40.000  
##      YCRole         YbtwnPromo         YwMgmt      
##  Min.   : 0.000   Min.   : 0.000   Min.   : 0.000  
##  1st Qu.: 2.000   1st Qu.: 0.000   1st Qu.: 2.000  
##  Median : 3.000   Median : 1.000   Median : 3.000  
##  Mean   : 4.229   Mean   : 2.188   Mean   : 4.123  
##  3rd Qu.: 7.000   3rd Qu.: 3.000   3rd Qu.: 7.000  
##  Max.   :18.000   Max.   :15.000   Max.   :17.000
```

```r
# review the class of the variables in the dataframe.
# Results indicate we are operating with character and numeric classes. 
lapply(Data, class) 
```

```
## $Age
## [1] "numeric"
## 
## $Attrition
## [1] "character"
## 
## $Feq.Travel
## [1] "character"
## 
## $Daily.Rate
## [1] "numeric"
## 
## $Department
## [1] "character"
## 
## $mlg.Home
## [1] "numeric"
## 
## $Education
## [1] "numeric"
## 
## $Ed.Field
## [1] "character"
## 
## $Emp.Count
## [1] "numeric"
## 
## $Emp.Number
## [1] "numeric"
## 
## $Env.Sat
## [1] "numeric"
## 
## $Gender
## [1] "character"
## 
## $HourlyRate
## [1] "numeric"
## 
## $Job.Invol
## [1] "numeric"
## 
## $Job.Level
## [1] "numeric"
## 
## $Title
## [1] "character"
## 
## $Satisfied
## [1] "numeric"
## 
## $M.S.D
## [1] "character"
## 
## $Income.mos
## [1] "numeric"
## 
## $Rate.mos
## [1] "numeric"
## 
## $Jobs.Worked
## [1] "numeric"
## 
## $Over18
## [1] "character"
## 
## $OT
## [1] "character"
## 
## $Percent.Inc
## [1] "numeric"
## 
## $Performance
## [1] "numeric"
## 
## $Sat.Relation
## [1] "numeric"
## 
## $Hours
## [1] "numeric"
## 
## $Stock
## [1] "numeric"
## 
## $Yrs.Wrkd
## [1] "numeric"
## 
## $Training
## [1] "numeric"
## 
## $Work.Life
## [1] "numeric"
## 
## $YOS
## [1] "numeric"
## 
## $YCRole
## [1] "numeric"
## 
## $YbtwnPromo
## [1] "numeric"
## 
## $YwMgmt
## [1] "numeric"
```

```r
# Tidy the data to manageable dataframe. 
# Reduce the number of col in the dataframe and call the new dataframe Small.
Small<- data.frame(Data$Attrition, Data$Age, Data$Gender, Data$M.S.D, Data$YOS, Data$Education,  Data$Ed.Field, Data$Title, Data$Rate.mos, Data$mlg.Home)      

#Change col names in the smaller dataframe. 
names <- c( "Attrition", "Age", "Gender", "M.S.D", "YOS", "Ed.Lvl", "Education", "Title", "Income.mos", "mlg.Home")
Small <- setNames (Small, names)
head(Small)
```

```
##   Attrition Age Gender   M.S.D YOS Ed.Lvl     Education
## 1       Yes  41 Female  Single   6      2 Life Sciences
## 2        No  49   Male Married  10      1 Life Sciences
## 3       Yes  37   Male  Single   0      2         Other
## 4        No  33 Female Married   8      4 Life Sciences
## 5        No  27   Male Married   2      1       Medical
## 6        No  32   Male  Single   7      2 Life Sciences
##                   Title Income.mos mlg.Home
## 1       Sales Executive      19479        1
## 2    Research Scientist      24907        8
## 3 Laboratory Technician       2396        2
## 4    Research Scientist      23159        3
## 5 Laboratory Technician      16632        2
## 6 Laboratory Technician      11864        2
```

### 3.a )   Is anyone under 18 participating in the study?

```r
Over18 <- grep("N", Small$Over18)
Over18
```

```
## integer(0)
```
Response is 0. So, all are considered over 18 by their response. There are 8 people who state they are 18 but we understand this response to be 18, plus a few days or months. There is no exclusion of data because of age in the study. 


### 3.b)  Provide descriptive Statistics on at least 7 variables.

```r
summary(Small)
```

```
##  Attrition       Age           Gender         M.S.D          YOS        
##  No :1233   Min.   :18.00   Female:588   Divorced:327   Min.   : 0.000  
##  Yes: 237   1st Qu.:30.00   Male  :882   Married :673   1st Qu.: 3.000  
##             Median :36.00                Single  :470   Median : 5.000  
##             Mean   :36.92                               Mean   : 7.008  
##             3rd Qu.:43.00                               3rd Qu.: 9.000  
##             Max.   :60.00                               Max.   :40.000  
##                                                                         
##      Ed.Lvl                 Education                         Title    
##  Min.   :1.000   Human Resources : 27   Sales Executive          :326  
##  1st Qu.:2.000   Life Sciences   :606   Research Scientist       :292  
##  Median :3.000   Marketing       :159   Laboratory Technician    :259  
##  Mean   :2.913   Medical         :464   Manufacturing Director   :145  
##  3rd Qu.:4.000   Other           : 82   Healthcare Representative:131  
##  Max.   :5.000   Technical Degree:132   Manager                  :102  
##                                         (Other)                  :215  
##    Income.mos       mlg.Home     
##  Min.   : 2094   Min.   : 1.000  
##  1st Qu.: 8047   1st Qu.: 2.000  
##  Median :14236   Median : 7.000  
##  Mean   :14313   Mean   : 9.193  
##  3rd Qu.:20462   3rd Qu.:14.000  
##  Max.   :26999   Max.   :29.000  
## 
```

### 3.c)  Provide a histogram for 2 of the variables. 

```r
# Plot Gender vs Number of Employees
plot(Small$Gender,  xlab = "Gender",   ylab= "Employees",  main="Men vs Women Ratio in Data Reviewed", ylim=c(0,1000), col=c("Yellow", "Blue"))
```

![](CaseStudy2_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

```r
#Plot Number of Employee Attrition vs Total Number of Employees.
plot(Small$Attrition , xlab = "Attrition in the Workforce",   ylab= "Employees",  main="Attrition considered in the Data Reviewed", col= c("Red", "Green"))
```

![](CaseStudy2_files/figure-html/unnamed-chunk-6-2.png)<!-- -->


# 3.d) Give Frequency for Gender, Education  and Occupation. How many are in management positions? 

```r
#Gender Summary Statistics.
summary(Small$Gender)
```

```
## Female   Male 
##    588    882
```

```r
#Education Field Summary Statistics.
summary(Small$Education)
```

```
##  Human Resources    Life Sciences        Marketing          Medical 
##               27              606              159              464 
##            Other Technical Degree 
##               82              132
```

```r
#Education Level Summary Statistics.
summary(Small$Ed.Lvl)  
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   1.000   2.000   3.000   2.913   4.000   5.000
```

```r
# Education
# 1 'Below College'
#	2 'College'
#	3 'Bachelor'
#	4 'Master'
#	5 'Doctor'

#Department titles and summary statistics.
summary(Small$Title)  
```

```
## Healthcare Representative           Human Resources 
##                       131                        52 
##     Laboratory Technician                   Manager 
##                       259                       102 
##    Manufacturing Director         Research Director 
##                       145                        80 
##        Research Scientist           Sales Executive 
##                       292                       326 
##      Sales Representative 
##                        83
```
Result : Number of management positions (Mfg and Research Directors, Sales Exec and Managers)
         Total (145 + 80 + 326 + 102) = 653

### Using only the data where Attrition is True. 

```r
New.Data <- read_xlsx("CaseStudy2-data.xlsx")
Data <- data.frame(New.Data)

names <- c( "Age", "Attrition", "Feq.Travel", "Daily.Rate", "Department", "mlg.Home", "Education", "Ed.Field", "Emp.Count", "Emp.Number", "Env.Sat", "Gender", "HourlyRate", "Job.Invol", "Job.Level", "Title", "Satisfied", "M.S.D", "Income.mos","Rate.mos", "Jobs.Worked", "Over18", "OT", "Percent.Inc" , "Performance", "Sat.Relation", "Hours", "Stock", "Yrs.Wrkd", "Training", "Work.Life", "YOS", "YCRole","YbtwnPromo", "YwMgmt")

Data <- setNames(Data, names)

Small <- data.frame(Data$Attrition, Data$Age, Data$Gender, Data$M.S.D, Data$YOS,   Data$Ed.Field, Data$Title, Data$Rate.mos, Data$mlg.Home)      

#Change col names in the smaller dataframe. 
names <- c( "Attrition", "Age", "Gender", "M.S.D", "YOS", "Education", "Title", "Income.mos", "mlg.Home")
Small <- setNames (Small, names)

#DF Small, modify qualitative variable attriation to a quantitaive boolean variable (where 1 is yes and no is 0).
Small$Attrition <- revalue(Small$Attrition, c("Yes"=1, "No" = 0)) 
#Show the dataframe Small was revalued with 1's and 0's in the Attrition column. 
head(Small$Attrition) 
```

```
## [1] 1 0 1 0 0 0
## Levels: 0 1
```

```r
#Create a dataframe called True.Attrition out of the dataframe Small. Pull out only the rows in Small for when the Attrition column is = 1.
True.Attrition <- subset(Small, Small$Attrition==1)  

#Show only the variables names the dataframe True.Attrition.
head(True.Attrition)
```

```
##    Attrition Age Gender  M.S.D YOS     Education                 Title
## 1          1  41 Female Single   6 Life Sciences       Sales Executive
## 3          1  37   Male Single   0         Other Laboratory Technician
## 15         1  28   Male Single   4 Life Sciences Laboratory Technician
## 22         1  36   Male Single   5 Life Sciences  Sales Representative
## 25         1  34   Male Single   4       Medical    Research Scientist
## 27         1  32 Female Single  10 Life Sciences    Research Scientist
##    Income.mos mlg.Home
## 1       19479        1
## 3        2396        2
## 15      12947       24
## 22       6986        9
## 25      17102        6
## 27       4681       16
```

```r
#Summary statistics on variables impacted by attrition.
summary(True.Attrition) 
```

```
##  Attrition      Age           Gender         M.S.D          YOS        
##  0:  0     Min.   :18.00   Female: 87   Divorced: 33   Min.   : 0.000  
##  1:237     1st Qu.:28.00   Male  :150   Married : 84   1st Qu.: 1.000  
##            Median :32.00                Single  :120   Median : 3.000  
##            Mean   :33.61                               Mean   : 5.131  
##            3rd Qu.:39.00                               3rd Qu.: 7.000  
##            Max.   :58.00                               Max.   :40.000  
##                                                                        
##             Education                     Title      Income.mos   
##  Human Resources : 7   Laboratory Technician :62   Min.   : 2326  
##  Life Sciences   :89   Sales Executive       :57   1st Qu.: 8870  
##  Marketing       :35   Research Scientist    :47   Median :14618  
##  Medical         :63   Sales Representative  :33   Mean   :14559  
##  Other           :11   Human Resources       :12   3rd Qu.:21081  
##  Technical Degree:32   Manufacturing Director:10   Max.   :26999  
##                        (Other)               :16                  
##     mlg.Home    
##  Min.   : 1.00  
##  1st Qu.: 3.00  
##  Median : 9.00  
##  Mean   :10.63  
##  3rd Qu.:17.00  
##  Max.   :29.00  
## 
```
When Years of Service is 0, the employee is indicating they have worked less than 1 year.


### Graph a histogram of employees who show attrition compared to their commute distance. 

```r
hist(True.Attrition$mlg.Home, 
     main="Miles from Home Impacting Attrition", 
     xlab="Miles from Home",
     ylab="Number of Employees ", 
     border="blue", 
     col="green")
```

![](CaseStudy2_files/figure-html/unnamed-chunk-9-1.png)<!-- -->

Results conclude distance from home appears to impact attrition. There is right skew to the data. Indicating those living close to their place of employment will attrition out of the company.

### Graph a histogram of employees who show attrition compared to the age of employee. 

```r
hist(True.Attrition$Age,
     main="Age of Employees Impacting Attrition", 
     xlab="Employees Age (years)",
     ylab="Number of Employees",
     border = "blue",
     col="yellow")
```

![](CaseStudy2_files/figure-html/unnamed-chunk-10-1.png)<!-- -->

The graphical results show a right skew. The older the age of the employee the less likely the company is to experience attrition. We show a spike of attrition between the age of 25 to 35. Outside of this specified age bracket attrition greatly decreases. 

### Variables impacting attrition. Review Department Titles compared to Gender. 

```r
library (ggplot2)
par(las=1)
Attrition.Gender <- ggplot(True.Attrition, aes(x=True.Attrition$Gender, y=True.Attrition$Title, fill = True.Attrition$Title)) + geom_bar(stat="identity", position="dodge") + xlab("Gender (Female/Male)") + ylab("Department Titles") + ggtitle("Attrition vs. Department") +   theme(plot.title = element_text(hjust = .5))

Attrition.Gender 
```

![](CaseStudy2_files/figure-html/unnamed-chunk-11-1.png)<!-- -->

Results indicate attrition is dominant in the Sales Executives and Sales Representative field for both men and women. This could largely be due to travel required. 

### Determine what the age bracket is for each department that displays attrition.

```r
par(las=1)
SalesvsAge <- ggplot(True.Attrition, aes(x=True.Attrition$Age, y=True.Attrition$Title, fill = True.Attrition$Title)) + geom_bar(stat="identity", position="dodge") + xlab("Age (years)") + ylab("Department Titles") + ggtitle("Department Title vs. Age in Attrition") +   theme(plot.title = element_text(hjust = .5))

SalesvsAge
```

![](CaseStudy2_files/figure-html/unnamed-chunk-12-1.png)<!-- -->

Results indicate the sales representative are dominantly 18-40, which coincides with the overall average
age for attrition which approximately 25-35 year old. We recommend to keep a younger sales team below the ### age of 25 or over the age of 35 to assist in reducing attrition. The workforce does have sales 
representative over 45 and in their mid 50's and the attrition rate of these age groups is significantly ### less. 

### What are the other influencial factors of attrition? Does being married, single or divorced have any impact on Sales Representatives. We show married people are less likely to cause attrition than single and divorced employees. What does this company have in attrition and marital status?


```r
par(las=1)
SalesvsMSD <- ggplot(True.Attrition, aes(x=True.Attrition$M.S.D, y=True.Attrition$Age, fill = True.Attrition$Title)) + geom_bar(stat="identity", position="dodge") + xlab("Married, Single, Divorced") + ylab("Number of Employees") + ggtitle("Attrition vs. Maritial Status") +   theme(plot.title = element_text(hjust = .5))
SalesvsMSD
```

![](CaseStudy2_files/figure-html/unnamed-chunk-13-1.png)<!-- -->

Results indicate there is dominating feature in marital status for Sales Representatives in the company. In fact, we have a significant number who are married and with married people showing less probability to attrition we do conclude marital status to be a role in attrition with this company in this department/title.


### 4.c   Is there a relationship between age and income, color each point based off of gender? 

```r
par(las=2)


Age2Income<-ggplot(New.Data, aes(x=Age, y=MonthlyIncome, group=Gender, color =Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm") + xlab("Age (years) of Employee") +  ylab("Monthly Income") + ggtitle("Workforce Income compared to Age") + theme(plot.title = element_text(hjust = 0.5))
Age2Income
```

![](CaseStudy2_files/figure-html/unnamed-chunk-14-1.png)<!-- -->

```r
LinearCorrelation <- lm(MonthlyIncome ~ Age, data = New.Data)
summary(LinearCorrelation)
```

```
## 
## Call:
## lm(formula = MonthlyIncome ~ Age, data = New.Data)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -9990.1 -2592.7  -677.9  1810.5 12540.8 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept) -2970.67     443.70  -6.695 3.06e-11 ***
## Age           256.57      11.67  21.995  < 2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 4084 on 1468 degrees of freedom
## Multiple R-squared:  0.2479,	Adjusted R-squared:  0.2473 
## F-statistic: 483.8 on 1 and 1468 DF,  p-value: < 2.2e-16
```

```r
Correlation.Age_Income <- sqrt(summary(LinearCorrelation)$r.squared)
Correlation.Age_Income
```

```
## [1] 0.4978546
```


```r
# Overall test when comparing both men and women in the workforce as one. 
# Original Linear Regression to discover correlation between Age and Income
ageincome.lm <- lm(MonthlyIncome ~ Age, data = New.Data)
ageincome.res <- resid(ageincome.lm)
summary(ageincome.lm)
```

```
## 
## Call:
## lm(formula = MonthlyIncome ~ Age, data = New.Data)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -9990.1 -2592.7  -677.9  1810.5 12540.8 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept) -2970.67     443.70  -6.695 3.06e-11 ***
## Age           256.57      11.67  21.995  < 2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 4084 on 1468 degrees of freedom
## Multiple R-squared:  0.2479,	Adjusted R-squared:  0.2473 
## F-statistic: 483.8 on 1 and 1468 DF,  p-value: < 2.2e-16
```

```r
# Simple Regression Model
plot(ageincome.lm)
```

![](CaseStudy2_files/figure-html/unnamed-chunk-15-1.png)<!-- -->![](CaseStudy2_files/figure-html/unnamed-chunk-15-2.png)<!-- -->![](CaseStudy2_files/figure-html/unnamed-chunk-15-3.png)<!-- -->![](CaseStudy2_files/figure-html/unnamed-chunk-15-4.png)<!-- -->

```r
plot(x = New.Data$Age, y = New.Data$MonthlyIncome, ylim=c(0,20000), xlab = "Age", ylab = "Income", main = "Age vs Income")
displayDF <- data.frame(New.Data)

# Regression Model
## Add the regression line to the existing scatterplot
abline(ageincome.lm, col = "red")
## Create "new" data to make confidence and prediction intervals
newx <- displayDF$Age
newx <- sort(newx)
## Confidence Internal
conf <- predict(ageincome.lm, newdata = data.frame(Age = newx), interval = c("confidence"), 
                type = c("response"), level = .95)
## Prediction Interval
pred <- predict(ageincome.lm, newdata = data.frame(Age = newx), interval = c("predict"), 
                type = c("response"), level = .95)
## Add prediction and confidence intervals to the scatterplot
lines(newx, conf[,2], col = "blue", lty = 2, lwd = 2)
lines(newx, conf[,3], col = "blue", lty = 2, lwd = 2)
lines(newx, pred[,2], col = "green", lty = 2, lwd = 2)
lines(newx, pred[,3], col = "green", lty = 2, lwd = 2)
```

![](CaseStudy2_files/figure-html/unnamed-chunk-15-5.png)<!-- -->

```r
## Residual Plot
plot(New.Data$Age, ageincome.res, ylab = "Residuals", xlab = "Year", main = "Residuals vs. Year")
abline(0,0)
```

![](CaseStudy2_files/figure-html/unnamed-chunk-15-6.png)<!-- -->

After checking assumptions we were able to determine that there is a correlation between age and income. The specific values pertaining to this are displayed above.

When we review the relationship between age to income in a regression split between men and women there is a small variance. Women have no significant change between age and income while men have a small increase in pay as they become older. Overall the variance is negligible  at ChemicalRepo.


## 4.d What about Life Satisfaction? Is there a discernable relationship there to what?  
### (Trends and Observations) In this study we margined out the Research Scientist. We reviewed the overall satisfaction levels of Research Scientist relative to the  distance they travel to work, their Age, their monthly Income, Marital Status and Years between Promotions.


```r
par(las=2)
# Subset out from the large dataframe Data only those who have the title Research Scientist.
DSJob <- subset(Data, Title=="Research Scientist")
```

## Other comparisons. 

All comparisons that have been observed with an ordered response are organized on a scale of 1 to 4, with 4 representing a response of "Very Highly Satisfied".

### Compare satisfaction in the overall workforce by Research Scientist in ChemicalRepo by their commute.


```r
# Total Workforce comparison of Satisfaction vs miles from home.
LifeSat2Home<-ggplot(Data, aes(x=mlg.Home, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Distance from Home") +  ylab("Satisfied with their Job") + ggtitle("Workforce Satisfied Life by Distance to Home") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
LifeSat2Home
```

![](CaseStudy2_files/figure-html/unnamed-chunk-17-1.png)<!-- -->

```r
LifeSat2Homelm <- lm(Satisfied ~ mlg.Home, data = Data)


# Research Scientist Satisfied vs miles from home.
LifeSat2HomeDS<-ggplot(DSJob, aes(x=mlg.Home, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Distance from Home") +  ylab("Satisfied with their Job") + ggtitle("Satisfied Life vs. Distance to Home for Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
LifeSat2HomeDS
```

![](CaseStudy2_files/figure-html/unnamed-chunk-17-2.png)<!-- -->

```r
LifeSat2HomeDSlm <- lm(Satisfied ~ mlg.Home, data = DSJob)
summary(LifeSat2HomeDSlm)
```

```
## 
## Call:
## lm(formula = Satisfied ~ mlg.Home, data = DSJob)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -1.9725 -0.7738  0.2262  1.1321  1.3098 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept) 2.679722   0.095826  27.964   <2e-16 ***
## mlg.Home    0.010456   0.007911   1.322    0.187    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 1.094 on 290 degrees of freedom
## Multiple R-squared:  0.005988,	Adjusted R-squared:  0.00256 
## F-statistic: 1.747 on 1 and 290 DF,  p-value: 0.1873
```


We can conclude the employees as a whole in ChemicalRepo report a  "Medium" to "High" satisfaction with the distance in commute. Men appear to be more satisfied than women in the workforce when they are observed to have a longer commute distance. When we review the Research Scientist specifically, they too have a positive correlation (as we see mileage increase we also saw satisfaction increase), and also that men are more satisfied than women when faced with longer commutes to work. This was an interesting factor for us, as both men and women who work as Research Scientist find a higher satisfaction with the company the more miles they drive to work.


### Compare Satisfaction in the overall workforce in ChemicalRepo by Age of employee.
### Compare Satisfaction by Research Scientist in ChemicalRepo Age of employee.

```r
# Total Workforce comparison of Satisfaction vs Age of employee.
Workforce.Age<-ggplot(Data, aes(x=Age, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Age (years)") +  ylab("Satisfied in their Job") + ggtitle("Workforce Satisfied Life vs. Age") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
Workforce.Age
```

![](CaseStudy2_files/figure-html/unnamed-chunk-18-1.png)<!-- -->

```r
# Research Scientist Satisfied vs Age of employee.
DS.Age<-ggplot(DSJob, aes(x=Age, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Age (years) of Research Scientist") +  ylab("Satisfied in their Job") + ggtitle("The Age of a Research Scientist Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5))
DS.Age
```

![](CaseStudy2_files/figure-html/unnamed-chunk-18-2.png)<!-- -->


We can conclude the employees as a whole in ChemicalRepo with men having a higher job satisfaction the older men become. As women grow older, they become less satisfied within the company. When reviewing the Research Scientist department, we find a very similar comparison for men and women. Women decline in job satisfaction at ChemicalRepo at an older age, while men increase within a small margin in job satisfaction at an older age in respect to the Research Scientist position.

### Compare Satisfaction in the overall workforce in ChemicalRepo by Marital Status.
### Compare Satisfaction by Research Scientist in ChemicalRepo by Marital Status.

```r
# Total Workforce comparison of Satisfaction vs Marital Status.
Workforce.Alter<-ggplot(Data, aes(x=M.S.D, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Married, Single, Divorced") +  ylab("Satisfied in their Job") + ggtitle("Workforce Satisfied Life vs. Marital Status") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
Workforce.Alter
```

![](CaseStudy2_files/figure-html/unnamed-chunk-19-1.png)<!-- -->

```r
# Research Scientist Satisfied vs Marital Status.
DS.Alter<-ggplot(DSJob, aes(x=M.S.D, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Married, Single, Divorced") +  ylab("Satisfied in their Job") + ggtitle("Married, Single and Divorced Research Scientist, Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
DS.Alter
```

![](CaseStudy2_files/figure-html/unnamed-chunk-19-2.png)<!-- -->


We can conclude that the male employees in ChemicalRepo are "Medium" to "Highly" satisfied. We are also able to conclude that women who are divorced are less satisfied than single women. Yet married women demonstrate the highest satisfaction rating of all three types of marital statuses. Married women are almost "Highly" satisfied at ChemicalRepo.  When reviewing Research Scientist women are consistent in job satisfaction at a "Medium" to "Highly" satisfied ranking. However, men who are married are closer to "highly satisfied" compared to their respectively lower, single and divorced Research Scientist. 

### Compare Satisfaction in the overall workforce in ChemicalRepo by Yrs between promotion.
### Compare Satisfaction by Research Scientist in ChemicalRepo by Yrs between promotion.

```r
# Total Workforce comparison of Satisfaction vs Years between Promotions.
Workforce.Promo<-ggplot(Data, aes(x=YbtwnPromo, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Years between Promotions") +  ylab("Satisfied in Job") + ggtitle("Workforce Satisfied Life vs. Years between Promotions") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
Workforce.Promo
```

![](CaseStudy2_files/figure-html/unnamed-chunk-20-1.png)<!-- -->

```r
# Research Scientist Satisfied vs Years between Promotions. 
DS.Promo <- ggplot(DSJob, aes(x=YbtwnPromo, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Years between Promotions") +  ylab("Satisfied in Job") + ggtitle("Years between Promotions vs. Satisfaction as a Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
DS.Promo
```

![](CaseStudy2_files/figure-html/unnamed-chunk-20-2.png)<!-- -->


We can conclude that the employees as a whole in ChemicalRepo are between "Medium" to "Highly" Satisfied in respect to the years between promotions. As to be expected, both women and men become slightly less satisfied in their Jobs the longer they wait between promotions. In review of employees titled as Research Scientist, women become less satisfied at a faster rate than men in years between promotions. Women max out at 10 years between promotion but men continue to wait longer as Research Scientist. This could be due to years of service within the company rather than the candidate being ignored for other reasons.


### Compare Satisfaction in the overall workforce in ChemicalRepo by Income earned per month.
### Compare Satisfaction by Research Scientist in ChemicalRepo by Income earned per month.

```r
# Total Workforce comparison of Satisfaction vs Income per month.
Workforce.Income<-ggplot(Data, aes(x=Income.mos, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Income per Month (dollars)") +  ylab("Satisfied in their Job") + ggtitle("Workforce Satisfied Life vs. Income per Month") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
Workforce.Income
```

![](CaseStudy2_files/figure-html/unnamed-chunk-21-1.png)<!-- -->

```r
# Compare income compared to job satisfaction (male vs female).
DS.Income <- ggplot(DSJob, aes(x=Income.mos, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab(" Monthly Income") +  ylab("Satisfied in their Job") + ggtitle("Income as a Research Scientist vs. Satisfied Job for Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
DS.Income
```

![](CaseStudy2_files/figure-html/unnamed-chunk-21-2.png)<!-- -->


We can conclude the employees as a whole in ChemicalRepo are between "Medium" to "Highly" Satisfied with the income or compensation they receive. While men have a slightly higher approval rating in job satisfaction compared to women with respects to income, the difference is marginal.  The results indicate as a Research Scientist, men are paid a higher monthly income overall. The more men are paid the less satisfied they are with work. They start with ranking their satisfaction beyond "Highly Satisfied" but as they increase past $5k a month, it's observed that their job satisfaction drops below that of women. Men who make almost $10k a month rank a "Medium Satisfaction" with the job.  Which is inversed to what most would consider as a normal response to an increase in pay.  We believe this could be contributed to an increase of demands on the male employees who are making more income. However, the more women are paid the more satisfied they are with the work they perform.

### How satisfied are Research Scientist in their job at ChemicalRepo. 

```r
DS.Attrition <- ggplot(DSJob, aes(x=Attrition, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab(" Attrition") +  ylab("Satisfied in their Job") + ggtitle("Attrition vs. Satisfied Job for Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()

DS.Attrition
```

![](CaseStudy2_files/figure-html/unnamed-chunk-22-1.png)<!-- -->


We can conclude that the Research Scientists that leave the company are still above the medium level of job satisfaction. Women who leave the company were slightly less pleased in their positions than men, yet they generally had the same values when they were employed in the company. We find Women are overall less satisfied in their job as Research Scientists than men. However, they both rank the job satisfaction between a "Medium" to "High" satisfaction. 

### 4.d  Looking only at life satisfaction data only for all of the employees in ChemicalRepo. 

```r
library(ggplot2)
par(las=2)

Turnover <-  ggplot(Data, aes(x=Jobs.Worked, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Jobs Worked") +  ylab("Satisfied in their Job") + ggtitle("Number of Jobs worked compaired to Satisfied Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
Turnover
```

![](CaseStudy2_files/figure-html/unnamed-chunk-23-1.png)<!-- -->



Results indicate women are happier when they start in the workforce. Women who frequently change employment demonstrate they have a less satisfied work experience. Men however can change the jobs equal to women and maintain the same satisfaction as they did when they took their 1st job.  There is no impact on men in being satisfied with work compared to the number of times men change employment. Overall womenand men share equal satisfaction working when they have changed employer less than 2.5 times. 

### How many former jobs is considered normal in ChemicalRepo?

```r
Age.Jobs <-  ggplot(Data, aes(x=Jobs.Worked, y=Age, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Jobs Worked") +  ylab("Age") + ggtitle("Number of Jobs worked compaired to Age ") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()

Age.Jobs
```

![](CaseStudy2_files/figure-html/unnamed-chunk-24-1.png)<!-- -->



Results also indicate on average both women and men between the approximate age of 33 to 45 change jobs at almost the same rate. On average both men and women by the age of 40 have changed jobs almost 5 times. When compared to the maximum attrition age between 25 to 35 observed that both men and women in their 30's could be working in their first occupation since graduating. We find the attrition relative to the employee taking their first job in the workforce and to the number of jobs at a young age could be summer or high school jobs, even possibly a work-study or school based job (TA/Tutor/Etc). The lowest attrition rates are found in those over 35, although it is worth noting that the age range 33 to 45 considers up to 8 jobs a normal average. Thus were are able to conclude that there is no apparent risk by this age bracket and this many number of jobs worked.

We recommend to either reduce the sales team to those below the age of 25 or increase it beyond 35 years of age. We also recommend, when hiring, do not hold back from hiring employees with at least 8 jobs before they are 45. We conclude this is normal and can be contributed to jobs held while in high school and college. Overall there is a larger section of men holding employment at ChemicalRepo by 60% of the workforce. We also determine those who live greater than 10 miles from their work are less likely to attrition. In conclusion ChemicalRepo could increase the number of females in their workforce, increase the hiring age beyond 35 years old for new employees and look for employees with a commute greater than 10 miles from the office.  Based off the information given, attrition will with reduce by concentration in this area of adjustments.

# CONCLUSION
We hypothesized sales representatives, age and overall commute distance contributes to attrition within a company. We find there is evidence to conclude the sales representatives, age and commute influence attrition. We have discovered that the longer that an employee works for the company, the more they will earn. We do add ChemicalRepo could increae the income in Female employees and increase the job satisfaction. We also found that an increase in commuting distance to work is a positive relationship, meaning employees who live further from work are generally more satisfied and that those who work furthest from home are most satisfied, and this also held true in the job role of a Research Scientist. 


```r
sessionInfo()
```

```
## R version 3.5.1 (2018-07-02)
## Platform: x86_64-apple-darwin15.6.0 (64-bit)
## Running under: macOS Sierra 10.12.6
## 
## Matrix products: default
## BLAS: /Library/Frameworks/R.framework/Versions/3.5/Resources/lib/libRblas.0.dylib
## LAPACK: /Library/Frameworks/R.framework/Versions/3.5/Resources/lib/libRlapack.dylib
## 
## locale:
## [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## other attached packages:
## [1] ggplot2_3.1.1 plyr_1.8.4    readxl_1.3.1 
## 
## loaded via a namespace (and not attached):
##  [1] Rcpp_1.0.0       bindr_0.1.1      knitr_1.21       magrittr_1.5    
##  [5] tidyselect_0.2.5 munsell_0.5.0    colorspace_1.3-2 R6_2.3.0        
##  [9] rlang_0.3.1      stringr_1.3.1    dplyr_0.7.8      tools_3.5.1     
## [13] grid_3.5.1       gtable_0.2.0     xfun_0.4         withr_2.1.2     
## [17] htmltools_0.3.6  assertthat_0.2.0 yaml_2.2.0       lazyeval_0.2.1  
## [21] digest_0.6.18    tibble_1.4.2     crayon_1.3.4     bindrcpp_0.2.2  
## [25] purrr_0.3.0      codetools_0.2-15 glue_1.3.0       evaluate_0.12   
## [29] rmarkdown_1.11   labeling_0.3     stringi_1.2.4    compiler_3.5.1  
## [33] pillar_1.3.1     cellranger_1.1.0 scales_1.0.0     pkgconfig_2.0.2
```


```r
#create a codebook
makeCodebook(Data, replace=TRUE)
```

```
## Data report generation is finished. Please wait while your output file is being rendered.
```

```r
#makeCodebook(Small, replace = TRUE)  #pull data for database Small
#makeCodebook(True.Attrition, replace = TRUE)  #pull data for database True.Attrition
#makeCodebook(DSJob, replace = TRUE)   #pull data for database DSJob
```

---
title: "CaseStudy2"
author: "Kari Theobald, Shane Weinstock, Jeremey Simpson, Gabe Gonzales"
date: "4/3/2019"
output:
  html_document:
    keep_md: yes
---

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
## loaded via a namespace (and not attached):
##  [1] compiler_3.5.1  magrittr_1.5    tools_3.5.1     htmltools_0.3.6
##  [5] yaml_2.2.0      Rcpp_1.0.0      stringi_1.2.4   rmarkdown_1.11 
##  [9] knitr_1.21      stringr_1.3.1   xfun_0.4        digest_0.6.18  
## [13] evaluate_0.12
```


```r
#install.packages("readxl")
#install.packages("ggplot2")

library(readxl)
setwd("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2")

# 2.a ) Read the CSV file (we have xlsx) into the dataset. Output how many rows and columns 
New.Data <- read_xlsx("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2/CaseStudy2-data.xlsx")
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

```r
# 2.b ) Change col names to less than 12 characters in the  dataframe. 
names <- c( "Age", "Attrition", "Feq.Travel", "Daily.Rate", "Department", "mlg.Home", "Education", "Ed.Field", "Emp.Count", "Emp.Number", "Env.Sat", "Gender", "HourlyRate", "Job.Invol", "Job.Level", "Title", "Satisfied", "M.S.D", "Income.mos","Rate.mos", "Jobs.Worked", "Over18", "OT", "Percent.Inc" , "Performance", "Sat.Relation", "Hours", "Stock", "Yrs.Wrkd", "Training", "Work.Life", "YOS", "YCRole","YbtwnPromo", "YwMgmt")

Data <- setNames(Data, names)

head(Data)  #check new names
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
lapply(Data, class) # review the class of the variables in the dataframe.
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
# Results indicate we are operating with character and numberic classes. 

# Tidy the data to managable dataframe. 
# Reduce the number of col in the dataframe and call it Small.Data
Small.Data <- data.frame(Data$Attrition, Data$Age, Data$Gender, Data$M.S.D, Data$YOS,   Data$Ed.Field, Data$Title, Data$Rate.mos, Data$mlg.Home)      

#Change col names in the smaller dataframe. 
names <- c( "Attrition", "Age", "Gender", "M.S.D", "YOS", "Education", "Title", "Income.mos", "mlg.Home")
Small.Data <- setNames (Small.Data, names)
head(Small.Data)
```

```
##   Attrition Age Gender   M.S.D YOS     Education                 Title
## 1       Yes  41 Female  Single   6 Life Sciences       Sales Executive
## 2        No  49   Male Married  10 Life Sciences    Research Scientist
## 3       Yes  37   Male  Single   0         Other Laboratory Technician
## 4        No  33 Female Married   8 Life Sciences    Research Scientist
## 5        No  27   Male Married   2       Medical Laboratory Technician
## 6        No  32   Male  Single   7 Life Sciences Laboratory Technician
##   Income.mos mlg.Home
## 1      19479        1
## 2      24907        8
## 3       2396        2
## 4      23159        3
## 5      16632        2
## 6      11864        2
```

```r
# 3.a )   Is anyone under 18 participating in the study?
Over18 <- grep("N", Small.Data$Over18)
Over18
```

```
## integer(0)
```

```r
# Repsonse is 0. So all are considered over 18 by their response. There are 8 people who state they are 18 but we understand this response to be 18, plus a few days or months. Therefore we are leaving them in the study. 

# 3.b)  Provide descriptive Statistics on 7 variables.
summary(Small.Data)
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
##             Education                         Title       Income.mos   
##  Human Resources : 27   Sales Executive          :326   Min.   : 2094  
##  Life Sciences   :606   Research Scientist       :292   1st Qu.: 8047  
##  Marketing       :159   Laboratory Technician    :259   Median :14236  
##  Medical         :464   Manufacturing Director   :145   Mean   :14313  
##  Other           : 82   Healthcare Representative:131   3rd Qu.:20462  
##  Technical Degree:132   Manager                  :102   Max.   :26999  
##                         (Other)                  :215                  
##     mlg.Home     
##  Min.   : 1.000  
##  1st Qu.: 2.000  
##  Median : 7.000  
##  Mean   : 9.193  
##  3rd Qu.:14.000  
##  Max.   :29.000  
## 
```

```r
# 3.c)  Provide a histogram for 2 of the variables. 
plot(Small.Data$Gender,  xlab = "Gender",   ylab= "Employees",  main="Men vs Women Ratio in Data Reviewed", col=c("Yellow", "Blue"))
```

![](CaseStudy2_files/figure-html/unnamed-chunk-2-1.png)<!-- -->

```r
plot(Small.Data$Attrition , xlab = "Attrition in the Workforce",   ylab= "Employees",  main="Attrition considered in the Data Reviewed", col= c("Red", "Green"))
```

![](CaseStudy2_files/figure-html/unnamed-chunk-2-2.png)<!-- -->

```r
# 3.d) Give Frequency for Gender, Education  and Occupation.
summary(Small.Data$Gender)
```

```
## Female   Male 
##    588    882
```

```r
# Result : Female   Male 
#           588    882 
summary(Small.Data$Education)
```

```
##  Human Resources    Life Sciences        Marketing          Medical 
##               27              606              159              464 
##            Other Technical Degree 
##               82              132
```

```r
# Result :  Human Resources    Life Sciences        Marketing          Medical            Other Technical Degree 
#              27              606                       159              464               82              132 
summary(Small.Data$Title)
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

```r
# Result : Number of managment positions (Mfg and Research Directors, Sales Exec and Managers)
#          Total (145 + 80 + 326 + 102) = 653
#Healthcare Representative           Human Resources     Laboratory Technician                   Manager 
#                      131                        52                       259                       102 
#   Manufacturing Director         Research Director        Research Scientist           Sales Executive 
#                      145                        80                       292                       326 
#     Sales Representative 
#                       83 
#
```


```r
#Using only the data where Attrition is True. 

setwd("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2")

New.Data <- read_xlsx("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2/CaseStudy2-data.xlsx")
```

```
## readxl works best with a newer version of the tibble package.
## You currently have tibble v1.4.2.
## Falling back to column name repair from tibble <= v1.4.2.
## Message displays once per session.
```

```r
Data <- data.frame(New.Data)

names <- c( "Age", "Attrition", "Feq.Travel", "Daily.Rate", "Department", "mlg.Home", "Education", "Ed.Field", "Emp.Count", "Emp.Number", "Env.Sat", "Gender", "HourlyRate", "Job.Invol", "Job.Level", "Title", "Satisfied", "M.S.D", "Income.mos","Rate.mos", "Jobs.Worked", "Over18", "OT", "Percent.Inc" , "Performance", "Sat.Relation", "Hours", "Stock", "Yrs.Wrkd", "Training", "Work.Life", "YOS", "YCRole","YbtwnPromo", "YwMgmt")

Data <- setNames(Data, names)

Small.Data <- data.frame(Data$Attrition, Data$Age, Data$Gender, Data$M.S.D, Data$YOS,   Data$Ed.Field, Data$Title, Data$Rate.mos, Data$mlg.Home)      

#Change col names in the smaller dataframe. 
names <- c( "Attrition", "Age", "Gender", "M.S.D", "YOS", "Education", "Title", "Income.mos", "mlg.Home")
Small.Data <- setNames (Small.Data, names)

library(plyr)
Small.Data$Attrition <- revalue(Small.Data$Attrition, c("Yes"=1, "No" = 0))
head(Small.Data$Attrition)
```

```
## [1] 1 0 1 0 0 0
## Levels: 0 1
```

```r
True.Attrition<- subset(Small.Data, Small.Data$Attrition==1)
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

```r
#Years of Service is minium 0. The employee has checked this to indicate they have worked less than 1 year. 

hist(True.Attrition$mlg.Home, 
     main="Miles from Home Impacting Attrition", 
     xlab="Miles from Home",
     ylab="Number of Employees ", 
     border="blue", 
     col="green")
```

![](CaseStudy2_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

```r
#The distance from home appears to impact attrition. There is right skew to the data. Indicating those living
#close to their place of employement will attrition out of the company.

hist(True.Attrition$Age,
     main="Age of Employees Impacting Attrition", 
     xlab="Employees Age (years)",
     ylab="Number of Employees",
     border = "blue",
     col="yellow")
```

![](CaseStudy2_files/figure-html/unnamed-chunk-3-2.png)<!-- -->

```r
#The Age shows a right skew with the older the age the less likely to leave a company.

summary(True.Attrition$Title)
```

```
## Healthcare Representative           Human Resources 
##                         9                        12 
##     Laboratory Technician                   Manager 
##                        62                         5 
##    Manufacturing Director         Research Director 
##                        10                         2 
##        Research Scientist           Sales Executive 
##                        47                        57 
##      Sales Representative 
##                        33
```
# 4.c   Is there a relationship between age and income, color each point based off of gender? 
# Yes there is a positive relationship betwen age and income. Older employees tend to make higher monthly income than younger employees. 


```r
library(ggplot2)
par(las=2)

Age2Income<-ggplot(Small.Data, aes(x=Age, y=Income.mos, group=Gender, color =Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm") + xlab("Age (years) of Employee") +  ylab("Monthly Income") + ggtitle("Workforce Income compared to Age") + theme(plot.title = element_text(hjust = 0.5))
Age2Income
```

![](CaseStudy2_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

#What about Life Satisfaction? Is there a discernable relationship there to what?  (Trends and Observations)
#In this study we margined out the Research Scientist. We reviewed the overall satisfaction levels of Research Scientist relative to the  distance they travel to work, their Age, their monthly Income, Marital Status and Years between Promotions. 


```r
library(ggplot2)
par(las=2)

LifeSat2Home<-ggplot(Data, aes(x=mlg.Home, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Distance from Home") +  ylab("Satisfied with their Job") + ggtitle("Satisfied Life by Distance to Home") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
LifeSat2Home
```

![](CaseStudy2_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

```r
library(plyr)
DSJob <- subset(Data, Title=="Research Scientist")

#### Below we are testing  how Research Scientist relate in the data tested. ###
# Comepare Age to Job satisfaction for men and women.
DS.Satisfied<-ggplot(DSJob, aes(x=Age, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Age (years) of Research Scientist") +  ylab("Satisfied in their Job") + ggtitle("The Age of a Research Scientist Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5))
DS.Satisfied
```

![](CaseStudy2_files/figure-html/unnamed-chunk-5-2.png)<!-- -->

```r
# Compare Marital Status to Job Satisfaction for men and women. 
DS.Alter<-ggplot(DSJob, aes(x=M.S.D, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Married, Single, Divorced") +  ylab("Satisfied in their Job") + ggtitle("The Age of a Research Scientist Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
DS.Alter
```

![](CaseStudy2_files/figure-html/unnamed-chunk-5-3.png)<!-- -->

```r
# Compare Years between Promotions to Job Satisfaction for men and women. 
DS.Promo <- ggplot(DSJob, aes(x=YbtwnPromo, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Satisfied in Job") +  ylab("Years between Promotions") + ggtitle("Years between Promotions compared to Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
DS.Promo
```

![](CaseStudy2_files/figure-html/unnamed-chunk-5-4.png)<!-- -->

```r
# Compare income compared to job satisfaction (male vs female). We see that men are paid more overall. The more men are paid the less satisfied they are with work. The more women are paid the more satisfied they are with working. 

DS.Income <- ggplot(DSJob, aes(x=Income.mos, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab(" Monthly Income") +  ylab("Satisfied in their Job") + ggtitle("Income as a Research Scientist compaired to Satisfied Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
DS.Income
```

![](CaseStudy2_files/figure-html/unnamed-chunk-5-5.png)<!-- -->

#4.d  Looking only at life satisfaction data only. With Life Satisfaction overall at its maximum. 

```r
library(ggplot2)
par(las=2)

Turnover <-  ggplot(Data, aes(x=Jobs.Worked, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Jobs Worked") +  ylab("Satisfied in their Job") + ggtitle("Number of Jobs worked compaired to Satisfied Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
Turnover
```

![](CaseStudy2_files/figure-html/unnamed-chunk-6-1.png)<!-- -->

```r
#This indicates women are happier when they start in the work force. Women who frequently change employment demonstrate they have #a less satified work experience. Men however can change the jobs equal to women and maintain the same satisfaction as they did #when they took their 1st job.  There is no impact on men in being satisified with work compared to the number of times men change #employment. Overall women and men share equal satisfaction working when they have changed employer less than 2.5 times.  
```

---
title: "Codebook"
author: "Kari Theobald, Shane Weinstock, Jeremy Simpson, Gabe Gonzales"
date: "4/3/2019"
output:
  html_document:
    keep_md: yes
---


# Data report for Database "Data and New.Data". Same variables and dimensions for each database.
The dataset examined has the following dimensions:


---------------------------------
Feature                    Result
------------------------ --------
Number of observations       1470

Number of variables            35
---------------------------------

# Data report for Database "Small"
The dataset examined has the following dimensions:


---------------------------------
Feature                    Result
------------------------ --------
Number of observations       1470

Number of variables            10
---------------------------------

# Data report for Database "True.Attrition"
The dataset examined has the following dimensions:


---------------------------------
Feature                    Result
------------------------ --------
Number of observations        237

Number of variables             9
---------------------------------

# Data report for Database "DSJob". A subset of the Database Data or New.Data for Research Scientist Titles only.
The dataset examined has the following dimensions:


---------------------------------
Feature                    Result
------------------------ --------
Number of observations        292

Number of variables            35
---------------------------------






# Codebook summary table

---------------------------------------------------------------------------
Label   Variable             Class         # unique  Missing  Description  
                                             values                        
------- -------------------- ----------- ---------- --------- -------------
        **[Age]**            numeric             43  0.00 %                

        **[Attrition]**      character            2  0.00 %                

        **[Feq.Travel]**     character            3  0.00 %                

        **[Daily.Rate]**     numeric            886  0.00 %                

        **[Department]**     character            3  0.00 %                

        **[mlg.Home]**       numeric             29  0.00 %                

        **[Education]**      numeric              5  0.00 %                

        **[Ed.Field]**       character            6  0.00 %                

        **[Emp.Count]**      numeric              1  0.00 %                

        **[Emp.Number]**     numeric           1470  0.00 %                

        **[Env.Sat]**        numeric              4  0.00 %                

        **[Gender]**         character            2  0.00 %                

        **[HourlyRate]**     numeric             71  0.00 %                

        **[Job.Invol]**      numeric              4  0.00 %                

        **[Job.Level]**      numeric              5  0.00 %                

        **[Title]**          character            9  0.00 %                

        **[Satisfied]**      numeric              4  0.00 %                

        **[M.S.D]**          character            3  0.00 %                

        **[Income.mos]**     numeric           1349  0.00 %                

        **[Rate.mos]**       numeric           1427  0.00 %                

        **[Jobs.Worked]**    numeric             10  0.00 %                

        **[Over18]**         character            1  0.00 %                

        **[OT]**             character            2  0.00 %                

        **[Percent.Inc]**    numeric             15  0.00 %                

        **[Performance]**    numeric              2  0.00 %                

        **[Sat.Relation]**   numeric              4  0.00 %                

        **[Hours]**          numeric              1  0.00 %                

        **[Stock]**          numeric              4  0.00 %                

        **[Yrs.Wrkd]**       numeric             40  0.00 %                

        **[Training]**       numeric              7  0.00 %                

        **[Work.Life]**      numeric              4  0.00 %                

        **[YOS]**            numeric             37  0.00 %                

        **[YCRole]**         numeric             19  0.00 %                

        **[YbtwnPromo]**     numeric             16  0.00 %                

        **[YwMgmt]**         numeric             18  0.00 %  
        
        **[Attrition]**      factor               2  0.00 %                

        **[Age]**            numeric             43  0.00 %                

        **[Gender]**         factor               2  0.00 %                

        **[M.S.D]**          factor               3  0.00 %                

        **[YOS]**            numeric             37  0.00 %                

        **[Ed.Lvl]**         numeric              5  0.00 %                

        **[Education]**      factor               6  0.00 %                

        **[Title]**          factor               9  0.00 %                

        **[Income.mos]**     numeric           1427  0.00 %                

        **[mlg.Home]**       numeric             29  0.00 % 
        
        **[Attrition]**      factor               1  0.00 %                

        **[Age]**            numeric             39  0.00 %                

        **[Gender]**         factor               2  0.00 %                

        **[M.S.D]**          factor               3  0.00 %                

        **[YOS]**            numeric             28  0.00 %                

        **[Education]**      factor               6  0.00 %                

        **[Title]**          factor               9  0.00 %                

        **[Income.mos]**     numeric            236  0.00 %                

        **[mlg.Home]**       numeric             29  0.00 % 
        
        **[Age]**            numeric             40  0.00 %                

        **[Attrition]**      character            2  0.00 %                

        **[Feq.Travel]**     character            3  0.00 %                

        **[Daily.Rate]**     numeric            261  0.00 %                

        **[Department]**     character            1  0.00 %                

        **[mlg.Home]**       numeric             29  0.00 %                

        **[Education]**      numeric              5  0.00 %                

        **[Ed.Field]**       character            4  0.00 %                

        **[Emp.Count]**      numeric              1  0.00 %                

        **[Emp.Number]**     numeric            292  0.00 %                

        **[Env.Sat]**        numeric              4  0.00 %                

        **[Gender]**         character            2  0.00 %                

        **[HourlyRate]**     numeric             71  0.00 %                

        **[Job.Invol]**      numeric              4  0.00 %                

        **[Job.Level]**      numeric              3  0.00 %                

        **[Title]**          character            1  0.00 %                

        **[Satisfied]**      numeric              4  0.00 %                

        **[M.S.D]**          character            3  0.00 %                

        **[Income.mos]**     numeric            274  0.00 %                

        **[Rate.mos]**       numeric            291  0.00 %                

        **[Jobs.Worked]**    numeric             10  0.00 %                

        **[Over18]**         character            1  0.00 %                

        **[OT]**             character            2  0.00 %                

        **[Percent.Inc]**    numeric             15  0.00 %                

        **[Performance]**    numeric              2  0.00 %                

        **[Sat.Relation]**   numeric              4  0.00 %                

        **[Hours]**          numeric              1  0.00 %                

        **[Stock]**          numeric              4  0.00 %                

        **[Yrs.Wrkd]**       numeric             22  0.00 %                

        **[Training]**       numeric              7  0.00 %                

        **[Work.Life]**      numeric              4  0.00 %                

        **[YOS]**            numeric             19  0.00 %                

        **[YCRole]**         numeric             15  0.00 %                

        **[YbtwnPromo]**     numeric             13  0.00 %                

        **[YwMgmt]**         numeric             14  0.00 % 

---------------------------------------------------------------------------




# Variable list
## Age

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          43

Median                           36

1st and 3rd quartiles        30; 43

Min. and max.                18; 60
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-1-Age-1.png)<!-- -->
</div>
</div>




---

## Attrition

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             2

Mode                             "No"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-2-Attrition-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"No\", \"Yes\". 



---

## Feq.Travel

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                     character

Number of missing obs.              0 (0 %)

Number of unique values                   3

Mode                        "Travel_Rarely"
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-3-Feq-Travel-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Non-Travel\", \"Travel_Frequently\", \"Travel_Rarely\". 



---

## Daily.Rate

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type                 numeric

Number of missing obs.        0 (0 %)

Number of unique values           886

Median                            802

1st and 3rd quartiles       465; 1157

Min. and max.               102; 1499
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-4-Daily-Rate-1.png)<!-- -->
</div>
</div>




---

## Department

<div class = "row">
<div class = "col-lg-8">

----------------------------------------------------
Feature                                       Result
------------------------- --------------------------
Variable type                              character

Number of missing obs.                       0 (0 %)

Number of unique values                            3

Mode                        "Research & Development"
----------------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-5-Department-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Human Resources\", \"Research & Development\", \"Sales\". 



---

## mlg.Home

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          29

Median                            7

1st and 3rd quartiles         2; 14

Min. and max.                 1; 29
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-6-mlg-Home-1.png)<!-- -->
</div>
</div>




---

## Education

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           5

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 5
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-7-Education-1.png)<!-- -->
</div>
</div>




---

## Ed.Field

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                     character

Number of missing obs.              0 (0 %)

Number of unique values                   6

Mode                        "Life Sciences"
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-8-Ed-Field-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Human Resources\", \"Life Sciences\", \"Marketing\", \"Medical\", \"Other\", \"Technical Degree\". 



---

## Emp.Count

* The variable only takes one (non-missing) value: \"1\". The variable contains 0 \% missing observations.



---

## Emp.Number

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                       numeric

Number of missing obs.              0 (0 %)

Number of unique values                1470

Median                               1020.5

1st and 3rd quartiles       491.25; 1555.75

Min. and max.                       1; 2068
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-10-Emp-Number-1.png)<!-- -->
</div>
</div>




---

## Env.Sat

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-11-Env-Sat-1.png)<!-- -->
</div>
</div>




---

## Gender

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             2

Mode                           "Male"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-12-Gender-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Female\", \"Male\". 



---

## HourlyRate

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type                 numeric

Number of missing obs.        0 (0 %)

Number of unique values            71

Median                             66

1st and 3rd quartiles       48; 83.75

Min. and max.                 30; 100
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-13-HourlyRate-1.png)<!-- -->
</div>
</div>




---

## Job.Invol

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 3

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-14-Job-Invol-1.png)<!-- -->
</div>
</div>




---

## Job.Level

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           5

Median                            2

1st and 3rd quartiles          1; 3

Min. and max.                  1; 5
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-15-Job-Level-1.png)<!-- -->
</div>
</div>




---

## Title

<div class = "row">
<div class = "col-lg-8">

---------------------------------------------
Feature                                Result
------------------------- -------------------
Variable type                       character

Number of missing obs.                0 (0 %)

Number of unique values                     9

Mode                        "Sales Executive"
---------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-16-Title-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Healthcare Representative\", \"Human Resources\", \"Laboratory Technician\", \"Manager\", \"Manufacturing Director\", \"Research Director\", \"Research Scientist\", \"Sales Executive\", \"Sales Representative\". 



---

## Satisfied

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-17-Satisfied-1.png)<!-- -->
</div>
</div>




---

## M.S.D

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             3

Mode                        "Married"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-18-M-S-D-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Divorced\", \"Married\", \"Single\". 



---

## Income.mos

<div class = "row">
<div class = "col-lg-8">

---------------------------------------
Feature                          Result
------------------------- -------------
Variable type                   numeric

Number of missing obs.          0 (0 %)

Number of unique values            1349

Median                             4919

1st and 3rd quartiles        2911; 8379

Min. and max.               1009; 19999
---------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-19-Income-mos-1.png)<!-- -->
</div>
</div>




---

## Rate.mos

<div class = "row">
<div class = "col-lg-8">

-----------------------------------------
Feature                            Result
------------------------- ---------------
Variable type                     numeric

Number of missing obs.            0 (0 %)

Number of unique values              1427

Median                            14235.5

1st and 3rd quartiles       8047; 20461.5

Min. and max.                 2094; 26999
-----------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-20-Rate-mos-1.png)<!-- -->
</div>
</div>




---

## Jobs.Worked

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          10

Median                            2

1st and 3rd quartiles          1; 4

Min. and max.                  0; 9
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-21-Jobs-Worked-1.png)<!-- -->
</div>
</div>




---

## Over18

* The variable only takes one (non-missing) value: \"Y\". The variable contains 0 \% missing observations.



---

## OT

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             2

Mode                             "No"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-23-OT-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"No\", \"Yes\". 



---

## Percent.Inc

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          15

Median                           14

1st and 3rd quartiles        12; 18

Min. and max.                11; 25
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-24-Percent-Inc-1.png)<!-- -->
</div>
</div>




---

## Performance

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           2

Median                            3

1st and 3rd quartiles          3; 3

Min. and max.                  3; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-25-Performance-1.png)<!-- -->
</div>
</div>




---

## Sat.Relation

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-26-Sat-Relation-1.png)<!-- -->
</div>
</div>




---

## Hours

* The variable only takes one (non-missing) value: \"80\". The variable contains 0 \% missing observations.



---

## Stock

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            1

1st and 3rd quartiles          0; 1

Min. and max.                  0; 3
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-28-Stock-1.png)<!-- -->
</div>
</div>




---

## Yrs.Wrkd

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          40

Median                           10

1st and 3rd quartiles         6; 15

Min. and max.                 0; 40
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-29-Yrs-Wrkd-1.png)<!-- -->
</div>
</div>




---

## Training

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           7

Median                            3

1st and 3rd quartiles          2; 3

Min. and max.                  0; 6
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-30-Training-1.png)<!-- -->
</div>
</div>




---

## Work.Life

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 3

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-31-Work-Life-1.png)<!-- -->
</div>
</div>




---

## YOS

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          37

Median                            5

1st and 3rd quartiles          3; 9

Min. and max.                 0; 40
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-32-YOS-1.png)<!-- -->
</div>
</div>




---

## YCRole

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          19

Median                            3

1st and 3rd quartiles          2; 7

Min. and max.                 0; 18
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-33-YCRole-1.png)<!-- -->
</div>
</div>




---

## YbtwnPromo

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          16

Median                            1

1st and 3rd quartiles          0; 3

Min. and max.                 0; 15
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-34-YbtwnPromo-1.png)<!-- -->
</div>
</div>




---

## YwMgmt

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          18

Median                            3

1st and 3rd quartiles          2; 7

Min. and max.                 0; 17
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-35-YwMgmt-1.png)<!-- -->
</div>
</div>


---

# Variable list for the Database "Small".

## Attrition

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type                factor

Number of missing obs.      0 (0 %)

Number of unique values           2

Mode                           "No"

Reference category               No
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-36-Attrition-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"No\", \"Yes\". 



---

## Age

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          43

Median                           36

1st and 3rd quartiles        30; 43

Min. and max.                18; 60
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-37-Age-1.png)<!-- -->
</div>
</div>




---

## Gender

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type                factor

Number of missing obs.      0 (0 %)

Number of unique values           2

Mode                         "Male"

Reference category           Female
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-38-Gender-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Female\", \"Male\". 



---

## M.S.D

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type                  factor

Number of missing obs.        0 (0 %)

Number of unique values             3

Mode                        "Married"

Reference category           Divorced
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-39-M-S-D-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Divorced\", \"Married\", \"Single\". 



---

## YOS

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          37

Median                            5

1st and 3rd quartiles          3; 9

Min. and max.                 0; 40
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-40-YOS-1.png)<!-- -->
</div>
</div>




---

## Ed.Lvl

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           5

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 5
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-41-Ed-Lvl-1.png)<!-- -->
</div>
</div>




---

## Education

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                        factor

Number of missing obs.              0 (0 %)

Number of unique values                   6

Mode                        "Life Sciences"

Reference category          Human Resources
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-42-Education-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Human Resources\", \"Life Sciences\", \"Marketing\", \"Medical\", \"Other\", \"Technical Degree\". 



---

## Title

<div class = "row">
<div class = "col-lg-8">

-----------------------------------------------------
Feature                                        Result
------------------------- ---------------------------
Variable type                                  factor

Number of missing obs.                        0 (0 %)

Number of unique values                             9

Mode                                "Sales Executive"

Reference category          Healthcare Representative
-----------------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-43-Title-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Healthcare Representative\", \"Human Resources\", \"Laboratory Technician\", \"Manager\", \"Manufacturing Director\", \"Research Director\", \"Research Scientist\", \"Sales Executive\", \"Sales Representative\". 



---

## Income.mos

<div class = "row">
<div class = "col-lg-8">

-----------------------------------------
Feature                            Result
------------------------- ---------------
Variable type                     numeric

Number of missing obs.            0 (0 %)

Number of unique values              1427

Median                            14235.5

1st and 3rd quartiles       8047; 20461.5

Min. and max.                 2094; 26999
-----------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-44-Income-mos-1.png)<!-- -->
</div>
</div>




---

## mlg.Home

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          29

Median                            7

1st and 3rd quartiles         2; 14

Min. and max.                 1; 29
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-45-mlg-Home-1.png)<!-- -->
</div>
</div>


---

# Varibale information in the Database "True.Attrition"

## Age

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          39

Median                           32

1st and 3rd quartiles        28; 39

Min. and max.                18; 58
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-46-Age-1.png)<!-- -->
</div>
</div>




---

## Gender

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type                factor

Number of missing obs.      0 (0 %)

Number of unique values           2

Mode                         "Male"

Reference category           Female
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-47-Gender-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Female\", \"Male\". 



---

## M.S.D

<div class = "row">
<div class = "col-lg-8">

------------------------------------
Feature                       Result
------------------------- ----------
Variable type                 factor

Number of missing obs.       0 (0 %)

Number of unique values            3

Mode                        "Single"

Reference category          Divorced
------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-48-M-S-D-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Divorced\", \"Married\", \"Single\". 



---

## YOS

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          28

Median                            3

1st and 3rd quartiles          1; 7

Min. and max.                 0; 40
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-49-YOS-1.png)<!-- -->
</div>
</div>




---

## Education

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                        factor

Number of missing obs.              0 (0 %)

Number of unique values                   6

Mode                        "Life Sciences"

Reference category          Human Resources
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-50-Education-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Human Resources\", \"Life Sciences\", \"Marketing\", \"Medical\", \"Other\", \"Technical Degree\". 



---

## Title

<div class = "row">
<div class = "col-lg-8">

-----------------------------------------------------
Feature                                        Result
------------------------- ---------------------------
Variable type                                  factor

Number of missing obs.                        0 (0 %)

Number of unique values                             9

Mode                          "Laboratory Technician"

Reference category          Healthcare Representative
-----------------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-51-Title-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Healthcare Representative\", \"Human Resources\", \"Laboratory Technician\", \"Manager\", \"Manufacturing Director\", \"Research Director\", \"Research Scientist\", \"Sales Executive\", \"Sales Representative\". 



---

## Income.mos

<div class = "row">
<div class = "col-lg-8">

---------------------------------------
Feature                          Result
------------------------- -------------
Variable type                   numeric

Number of missing obs.          0 (0 %)

Number of unique values             236

Median                            14618

1st and 3rd quartiles       8870; 21081

Min. and max.               2326; 26999
---------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-52-Income-mos-1.png)<!-- -->
</div>
</div>




---

## mlg.Home

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          29

Median                            9

1st and 3rd quartiles         3; 17

Min. and max.                 1; 29
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-53-mlg-Home-1.png)<!-- -->
</div>
</div>


---
# Variable list for DSJob (Subset).
## Age

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          40

Median                           33

1st and 3rd quartiles        28; 39

Min. and max.                18; 59
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-54-Age-1.png)<!-- -->
</div>
</div>




---

## Attrition

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             2

Mode                             "No"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-55-Attrition-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"No\", \"Yes\". 



---

## Feq.Travel

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                     character

Number of missing obs.              0 (0 %)

Number of unique values                   3

Mode                        "Travel_Rarely"
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-56-Feq-Travel-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Non-Travel\", \"Travel_Frequently\", \"Travel_Rarely\". 



---

## Daily.Rate

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                       numeric

Number of missing obs.              0 (0 %)

Number of unique values                 261

Median                                821.5

1st and 3rd quartiles       467.25; 1132.25

Min. and max.                     111; 1470
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-57-Daily-Rate-1.png)<!-- -->
</div>
</div>




---

## Department

* The variable only takes one (non-missing) value: \"Research & Development\". The variable contains 0 \% missing observations.



---

## mlg.Home

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          29

Median                          6.5

1st and 3rd quartiles         2; 14

Min. and max.                 1; 29
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-59-mlg-Home-1.png)<!-- -->
</div>
</div>




---

## Education

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           5

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 5
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-60-Education-1.png)<!-- -->
</div>
</div>




---

## Ed.Field

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                     character

Number of missing obs.              0 (0 %)

Number of unique values                   4

Mode                        "Life Sciences"
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-61-Ed-Field-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Life Sciences\", \"Medical\", \"Other\", \"Technical Degree\". 



---

## Emp.Count

* The variable only takes one (non-missing) value: \"1\". The variable contains 0 \% missing observations.



---

## Emp.Number

<div class = "row">
<div class = "col-lg-8">

-------------------------------------------
Feature                              Result
------------------------- -----------------
Variable type                       numeric

Number of missing obs.              0 (0 %)

Number of unique values                 292

Median                                999.5

1st and 3rd quartiles       437.75; 1548.25

Min. and max.                       2; 2054
-------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-63-Emp-Number-1.png)<!-- -->
</div>
</div>




---

## Env.Sat

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-64-Env-Sat-1.png)<!-- -->
</div>
</div>




---

## Gender

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             2

Mode                           "Male"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-65-Gender-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Female\", \"Male\". 



---

## HourlyRate

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type                 numeric

Number of missing obs.        0 (0 %)

Number of unique values            71

Median                             67

1st and 3rd quartiles       49.75; 83

Min. and max.                 30; 100
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-66-HourlyRate-1.png)<!-- -->
</div>
</div>




---

## Job.Invol

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 3

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-67-Job-Invol-1.png)<!-- -->
</div>
</div>




---

## Job.Level

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           3

Median                            1

1st and 3rd quartiles          1; 1

Min. and max.                  1; 3
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-68-Job-Level-1.png)<!-- -->
</div>
</div>




---

## Title

* The variable only takes one (non-missing) value: \"Research Scientist\". The variable contains 0 \% missing observations.



---

## Satisfied

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-70-Satisfied-1.png)<!-- -->
</div>
</div>




---

## M.S.D

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             3

Mode                        "Married"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-71-M-S-D-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"Divorced\", \"Married\", \"Single\". 



---

## Income.mos

<div class = "row">
<div class = "col-lg-8">

----------------------------------------
Feature                           Result
------------------------- --------------
Variable type                    numeric

Number of missing obs.           0 (0 %)

Number of unique values              274

Median                            2887.5

1st and 3rd quartiles       2386; 3902.5

Min. and max.                 1009; 9724
----------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-72-Income-mos-1.png)<!-- -->
</div>
</div>




---

## Rate.mos

<div class = "row">
<div class = "col-lg-8">

------------------------------------------
Feature                             Result
------------------------- ----------------
Variable type                      numeric

Number of missing obs.             0 (0 %)

Number of unique values                291

Median                               13522

1st and 3rd quartiles       7637; 19987.25

Min. and max.                  2122; 26999
------------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-73-Rate-mos-1.png)<!-- -->
</div>
</div>




---

## Jobs.Worked

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          10

Median                            1

1st and 3rd quartiles          1; 4

Min. and max.                  0; 9
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-74-Jobs-Worked-1.png)<!-- -->
</div>
</div>




---

## Over18

* The variable only takes one (non-missing) value: \"Y\". The variable contains 0 \% missing observations.



---

## OT

<div class = "row">
<div class = "col-lg-8">

-------------------------------------
Feature                        Result
------------------------- -----------
Variable type               character

Number of missing obs.        0 (0 %)

Number of unique values             2

Mode                             "No"
-------------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-76-OT-1.png)<!-- -->
</div>
</div>


- Observed factor levels: \"No\", \"Yes\". 



---

## Percent.Inc

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          15

Median                           14

1st and 3rd quartiles        13; 18

Min. and max.                11; 25
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-77-Percent-Inc-1.png)<!-- -->
</div>
</div>




---

## Performance

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           2

Median                            3

1st and 3rd quartiles          3; 3

Min. and max.                  3; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-78-Performance-1.png)<!-- -->
</div>
</div>




---

## Sat.Relation

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 4

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-79-Sat-Relation-1.png)<!-- -->
</div>
</div>




---

## Hours

* The variable only takes one (non-missing) value: \"80\". The variable contains 0 \% missing observations.



---

## Stock

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            1

1st and 3rd quartiles          0; 1

Min. and max.                  0; 3
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-81-Stock-1.png)<!-- -->
</div>
</div>




---

## Yrs.Wrkd

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          22

Median                            7

1st and 3rd quartiles         5; 10

Min. and max.                 0; 25
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-82-Yrs-Wrkd-1.png)<!-- -->
</div>
</div>




---

## Training

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           7

Median                            3

1st and 3rd quartiles          2; 3

Min. and max.                  0; 6
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-83-Training-1.png)<!-- -->
</div>
</div>




---

## Work.Life

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values           4

Median                            3

1st and 3rd quartiles          2; 3

Min. and max.                  1; 4
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-84-Work-Life-1.png)<!-- -->
</div>
</div>




---

## YOS

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          19

Median                          4.5

1st and 3rd quartiles          2; 7

Min. and max.                 0; 20
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-85-YOS-1.png)<!-- -->
</div>
</div>




---

## YCRole

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          15

Median                            2

1st and 3rd quartiles          2; 4

Min. and max.                 0; 15
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-86-YCRole-1.png)<!-- -->
</div>
</div>




---

## YbtwnPromo

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          13

Median                            1

1st and 3rd quartiles          0; 2

Min. and max.                 0; 13
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-87-YbtwnPromo-1.png)<!-- -->
</div>
</div>




---

## YwMgmt

<div class = "row">
<div class = "col-lg-8">

-----------------------------------
Feature                      Result
------------------------- ---------
Variable type               numeric

Number of missing obs.      0 (0 %)

Number of unique values          14

Median                            2

1st and 3rd quartiles          1; 5

Min. and max.                 0; 17
-----------------------------------


</div>
<div class = "col-lg-4">
![](Codebook_files/figure-html/Var-88-YwMgmt-1.png)<!-- -->
</div>
</div>




---




Report generation information:

 *  dataMaid v1.2.0 [Pkg: 2018-10-03 from CRAN (R 3.5.0)]

 *  R version 3.5.1 (2018-07-02).

 *  Platform: x86_64-apple-darwin15.6.0 (64-bit)(macOS Sierra 10.12.6).

 *  Function call: `makeDataReport(data = Data, mode = c("summarize", "visualize", 
"check"), smartNum = FALSE, file = "codebook_Data.Rmd", replace = TRUE, 
    checks = list(character = "showAllFactorLevels", factor = "showAllFactorLevels", 
        labelled = "showAllFactorLevels", haven_labelled = "showAllFactorLevels", 
        numeric = NULL, integer = NULL, logical = NULL, Date = NULL), 
    listChecks = FALSE, maxProbVals = Inf, codebook = TRUE, reportTitle = "Codebook for Data")`


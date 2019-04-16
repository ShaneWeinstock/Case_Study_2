# Case_Study_2
## Group 3

 Git repository project entitled "Case Study 2." Members of this project include Kari Theobald, Shane Weinstock, Jeremy Simpson and Gabriel Gonzales

## Introduction: This presentation provides an overview of exactly what type of exploratory data analysis (EDA) was performed on the dataset (CaseStudy2-data) provided by the client, ChemicalRepo. The client requested answers to the following questions:

### The top three factors contributing to employee turnover (attrition)
### Provide descriptive statistics on at least seven variables
### Give the frequencies for Gender, Education and Income
### Give counts of management positions
### Determine of a relationship exists between Age and Income
### Discern a possible relationship (correlation) between Life Satisfaction and another variable

## First, install necessary packages and libraries in R
### install.packages("readxl")
### install.packages("ggplot2")
### library(readxl)
### library(plyr)
### library(ggplot2)
### library(plyr)

## Now establish your working directory
### setwd("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2")

## 2.a ) Read the CSV file (we have xlsx) into the dataset call it Data. Output how many rows and columns
### New.Data <- read_xlsx("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2/CaseStudy2-data.xlsx")
### Data <- data.frame(New.Data)
### dim(Data)

## 2.b ) Change col names to less than 12 characters in the dataframe.
### names <- c( "Age", "Attrition", "Feq.Travel", "Daily.Rate", "Department", "mlg.Home", "Education", "Ed.Field", "Emp.Count", "Emp.Number", "Env.Sat", "Gender", "HourlyRate", "Job.Invol", "Job.Level", "Title", "Satisfied", "M.S.D", "Income.mos","Rate.mos", "Jobs.Worked", "Over18", "OT", "Percent.Inc" , "Performance", "Sat.Relation", "Hours", "Stock", "Yrs.Wrkd", "Training", "Work.Life", "YOS", "YCRole","YbtwnPromo", "YwMgmt")
### Data <- setNames(Data, names)

## Check your names
### head(Data) 

##  review the class of the variables in the dataframe
### lapply(Data, class)

## Tidy the data to manageable dataframe.
##  Reduce the number of col in the dataframe and call the new dataframe Small.
### Small<- data.frame(Data$Attrition, Data$Age, Data$Gender, Data$M.S.D, Data$YOS, Data$Education, Data$Ed.Field, Data$Title, Data$Rate.mos, Data$mlg.Home) 

## Change col names in the smaller dataframe
### names <- c( "Attrition", "Age", "Gender", "M.S.D", "YOS", "Ed.Lvl", "Education", "Title", "Income.mos", "mlg.Home")
### Small <- setNames (Small, names)

## Check names
### head(Small)

## 3.a ) Is anyone under 18 participating in the study?
### Over18 <- grep("N", Small$Over18)
### Over18
Response	is	0.	So,	all	are	considered	over	18	by	their	response.	There	are	8	people	who	
state	they	are	18	but	we	understand	this	response	to	be	18,	plus	a	few	days	or	months.	
There	is	no	exclusion	of	data	because	of	age	in	the	study.

## 3.b) Provide descriptive Statistics on at least 7 variables.
### summary(Small)

## 3.c) Provide a histogram for 2 of the variables
## Plot Gender vs Number of Employees
### plot(Small$Gender, xlab = "Gender", ylab= "Employees", main="Men vs Women Ratio in Data Reviewed", ylim=c(0,1000), col=c("Yellow", "Blue"))

## Plot Number of Employee Attrition vs Total Number of Employees
### plot(Small$Attrition , xlab = "Attrition in the Workforce", ylab= "Employees", main="Attrition considered in the Data Reviewed", col= c("Red", "Green"))

## 3.d) Give Frequency for Gender, Education and Occupation. How many are in management positions?
## Gender Summary Statistics
### summary(Small$Gender) 

## Education Field Summary Statistics
### summary(Small$Education)

## Education Level Summary Statistics
### summary(Small$Ed.Lvl)

## Department titles and summary statistics
### summary(Small$Title) 

Result	:	Number	of	management	positions	(Mfg	and	Research	Directors,	Sales	Exec	and	
Managers)	Total	(145	+	80	+	326	+	102)	=	653

## Using only the data where Attrition is True
### New.Data <- read_xlsx("~/Desktop/Kari/SMU /Doing Data Science/Homework/CaseStudy2/CaseStudy2/CaseStudy2-data.xlsx")
### Data <- data.frame(New.Data)

### names <- c( "Age", "Attrition", "Feq.Travel", "Daily.Rate", "Department", "mlg.Home", "Education", "Ed.Field", "Emp.Count", "Emp.Number", "Env.Sat", "Gender", "HourlyRate", "Job.Invol", "Job.Level", "Title", "Satisfied", "M.S.D", "Income.mos","Rate.mos", "Jobs.Worked", "Over18", "OT",  "Percent.Inc" , "Performance", "Sat.Relation", "Hours", "Stock", "Yrs.Wrkd", "Training", "Work.Life", "YOS", "YCRole","YbtwnPromo", "YwMgmt")

### Data <- setNames(Data, names)

### Small <- data.frame(Data$Attrition, Data$Age, Data$Gender, Data$M.S.D, Data$YOS, Data$Ed.Field, Data$Title, Data$Rate.mos, Data$mlg.Home)

## Change col names in the smaller dataframe
### names <- c( "Attrition", "Age", "Gender", "M.S.D", "YOS", "Education", "Title", "Income.mos", "mlg.Home")
### Small <- setNames (Small, names)

##  DF Small, change in the Attrition column all Yes answers to 1 and all No answers to 0
### Small$Attrition <- revalue(Small$Attrition, c("Yes"=1, "No" = 0))

##  Show the dataframe Small was revalued with 1's and 0's in the Attrition column
### head(Small$Attrition)

## Create a dataframe called True.Attrition out of the dataframe Small. Pull out only the rows in Small for when the Attrition column is = 1
### True.Attrition<- subset(Small, Small$Attrition==1)

## show only the variables names the dataframe True.Attrition
### head(True.Attrition) 

## summary statistics on variables impacted by attrition
### summary(True.Attrition)

When	Years	of	Service	is	0,	the	employee	is	indicating	they	have	worked	less	than	1	year.

## Graph a histogram of Attrition employees compared to commute distance
### hist(True.Attrition$mlg.Home,
### main="Miles from Home Impacting Attrition",
### xlab="Miles from Home",
### ylab="Number of Employees ",
### border="blue",
### col="green")

Results	conclude	distance	from	home	appears	to	impact	attrition.	There	is	right	skew	to	the	
data.	Indicating	those	living	close	to	their	place	of	employment	will	attrition	out	of	the	
company

## Graph a histogram of Attrition employees compared to age of employee
### hist(True.Attrition$Age,
### main="Age of Employees Impacting Attrition",
### xlab="Employees Age (years)",
### ylab="Number of Employees",
### border = "blue",
### col="yellow")

The	graphical	results	show	a	right	skew.	The	older	the	age	of	the	employee,	it	is	less	likely	
for	the	company	to	experience	attrition.	We	show	a	spike	of	attrition	between	the	age	of	25	
to	35.	Outside	of	the	age	bracket	the	attrition	goes	down.

## Variables impacting attrition. Review Department Titles compared to Gender
### library (ggplot2)
### par(las=1)
### Attrition.Gender <- ggplot(True.Attrition, aes(x=True.Attrition$Gender,
### y=True.Attrition$Title, fill = True.Attrition$Title)) +
### geom_bar(stat="identity", position="dodge") + xlab("Gender (Female/Male)") +
### ylab("Department Titles") + ggtitle("Attrition vs. Department") +
### theme(plot.title = element_text(hjust = .5))

### Attrition.Gender

 Results	indicate	attrition	is	dominant	in	the	Sales	Executives	and	Sales	Representative	field	 for	both	men	and	women.	This	could	largely	be	due	to	travel	required.

## Determine what is the age bracket is for each department that is showing attrition
### par(las=1)
### SalesvsAge <- ggplot(True.Attrition, aes(x=True.Attrition$Age,
### y=True.Attrition$Title, fill = True.Attrition$Title)) +
### geom_bar(stat="identity", position="dodge") + xlab("Age (years)") +
### ylab("Department Titles") + ggtitle("Department Title vs. Age in Attrition")
### + theme(plot.title = element_text(hjust = .5))

### SalesvsAge

Results	indicate	the	sales	representative	are	dominantly	18-40,	which	coincides	with	the	
overall	average	age	for	attrition	which	approximately	25-35	year	old.	We	recommend	to	
keep	a	younger	sales	team	below	the	###	age	of	25	or	over	the	age	of	35	to	assist in	
reducing	attrition.	The	workforce	does	have	sales	representative	over	45	and	in	their	mid	
50’s	and	the	attrition	rate	of	these	age	groups	is	significantly	###	less.

## What are other influential facotrs on attrition? Does being married, single or divorced have anyimpact on Sales Representatives. We show married people are less likely to cause attrition than single and divorced employees. What does this company have in attrition and marital status?

### par(las=1)
### SalesvsMSD <- ggplot(True.Attrition, aes(x=True.Attrition$M.S.D,
### y=True.Attrition$Age, fill = True.Attrition$Title)) +
### geom_bar(stat="identity", position="dodge") + xlab("Married, Single,
### Divorced") + ylab("Number of Employees") + ggtitle("Attrition vs. Maritial
### Status") + theme(plot.title = element_text(hjust = .5))

### SalesvsMSD

Results	indicate	there	is	dominating	feature	in	marital	status	for	Sales	Representatives	in	
the	company.	In	fact,	we	have	a	significant	number	who	are	married	and	with	married	
people	showing	less	probability	to	attrition	we	do	conclude	marital	status	to	be	a	role	in	
attrition	with	this	company	in	this	department/title.

## 4.c Is there a relationship between age and income, color each point based off of gender?

### par(las=2)

### Age2Income<-ggplot(Small, aes(x=Age, y=Income.mos, group=Gender, color
### =Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method="lm") +
### xlab("Age (years) of Employee") + ylab("Monthly Income") +
### ggtitle("Workforce Income compared to Age") + theme(plot.title = element_text(hjust = 0.5))
### Age2Income

### LinearCorrelation <- lm(MonthlyIncome ~ Age, data = New.Data)
### summary(LinearCorrelation)
### Correlation.Age_Income <- sqrt(summary(LinearCorrelation)$r.squared)
### Correlation.Age_Income

## Overall test when comparing both men and women in the workforce as one
### ageincome.lm <- lm(Income.mos ~ Age, data = Small)

## Original Linear Regression to discover correlation between Age and Income
### ageincome.res <- resid(ageincome.lm)
### summary(ageincome.lm)

## Simple Regression Model
### plot(ageincome.lm)

### plot(x = Small$Age, y = Small$Income.mos, ylim=c(0,50000), xlab = "Age", ylab = "Income", main = "Age vs Income") displayDF <- data.frame(Small)

## Regression Model
##  Add the regression line to the existing scatterplot
### abline(ageincome.lm, col = "red")

## Create "new" data to make confidence and prediction intervals
### newx <- displayDF$Age
### newx <- sort(newx)

## Confidence Internal
### conf <- predict(ageincome.lm, newdata = data.frame(Age = newx), interval = c("confidence"), type = c("response"), level = .95)
 
## Prediction Interval
### pred <- predict(ageincome.lm, newdata = data.frame(Age = newx), interval = c("predict"), type = c("response"), level = .95)

## Add prediction and confidence intervals to the scatterplot
### lines(newx, conf[,2], col = "blue", lty = 2, lwd = 2)
### lines(newx, conf[,3], col = "blue", lty = 2, lwd = 2)
### lines(newx, pred[,2], col = "green", lty = 2, lwd = 2)
### lines(newx, pred[,3], col = "green", lty = 2, lwd = 2)

## Residual Plot
### plot(Small$Age, ageincome.res, ylab = "Residuals", xlab = "Year", main = "Residuals vs. Year")
### abline(0,0)

After checking assumptions we were able to determine that there is a correlation between age and income. The specific values pertaining to this are displayed above.

When we review the relationship between age to income in a regression split between men and women there is a small variance. Women have no significant change between age and income while men have a small increase in pay as they become older. Overall the variance is negligible at ChemicalRepo.

## 4.d What about Life Satisfaction? Is there a discernable relationship there to what? (Trends and Observations) In this study we margined out the Research Scientist. We reviewed the overall satisfaction levels of Research Scientist relative to the distance they travel to work, their Age, their monthly Income, Marital Status and Years between Promotions.

## #subset out from the large dataframe Data only those who have the title Research Scientist.
### DSJob <- subset(Data, Title=="Research Scientist") 

## Other comparisons.
All comparisons that have been observed with an ordered response are organized on a scale of 1 to 4, with 4 representing a response of "Very Highly Satisfied".

## Compare Satisfaction in the overall workforce in ChemicalRepo by commute distance. (miles from home).
## Compare Satisfaction by Research Scientist in ChemicalRepo by their commute.

## Total Workforce comparison of Satisfaction vs miles from home.
### LifeSat2Home<-ggplot(Data, aes(x=mlg.Home, y=Satisfied, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Distance from Home") + ylab("Satisfied with their Job") + ggtitle("Workforce Satisfied Life by Distance to Home") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### LifeSat2Home
## LifeSat2Homelm <- lm(Satisfied ~ mlg.Home, data = Data)

## Research Scientist Satisfied vs miles from home
### LifeSat2HomeDS<-ggplot(DSJob, aes(x=mlg.Home, y=Satisfied, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Distance from Home") + ylab("Satisfied with their Job") + ggtitle("Satisfied Life vs. Distance to Home for Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### LifeSat2HomeDS
### LifeSat2HomeDSlm <- lm(Satisfied ~ mlg.Home, data = DSJob)
### summary(LifeSat2HomeDSlm)

We can conclude the employees as a whole in ChemicalRepo report a  "Medium" to "High" satisfaction with the distance in commute. Men appear to be more satisfied than women in the workforce when they are observed to have a longer commute distance. When we review the Research Scientist specifically, they too have a positive correlation (as we see mileage increase we also saw satisfaction increase), and also that men are more satisfied than women when faced with longer commutes to work. This was an interesting factor for us, as both men and women who work as Research Scientist find a higher satisfaction with the company the more miles they drive to work.

## Compare Satisfaction in the overall workforce in ChemicalRepo by Age of employee.
## Compare Satisfaction by Research Scientist in ChemicalRepo Age of employee.

## Total Workforce comparison of Satisfaction vs Age of employee.
### Workforce.Age<-ggplot(Data, aes(x=Age, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Age (years)") +  ylab("Satisfied in their Job") + ggtitle("Workforce Satisfied Life vs. Age") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### Workforce.Age

## Research Scientist Satisfied vs Age of employee.
### DS.Age<-ggplot(DSJob, aes(x=Age, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Age (years) of Research Scientist") +  ylab("Satisfied in their Job") + ggtitle("The Age of a Research Scientist Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5))
### DS.Age

We can conclude the employees as a whole in ChemicalRepo with men having a higher job satisfaction the older men become. As women grow older, they become less satisfied within the company. When reviewing the Research Scientist department, we find a very similar comparison for men and women. Women decline in job satisfaction at ChemicalRepo at an older age, while men increase within a small margin in job satisfaction at an older age in respect to the Research Scientist position.

## Compare Satisfaction in the overall workforce in ChemicalRepo by Marital Status.
## Compare Satisfaction by Research Scientist in ChemicalRepo by Marital Status.

## Total Workforce comparison of Satisfaction vs Marital Status.
### Workforce.Alter<-ggplot(Data, aes(x=M.S.D, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Married, Single, Divorced") +  ylab("Satisfied in their Job") + ggtitle("Workforce Satisfied Life vs. Marital Status") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### Workforce.Alter

## Research Scientist Satisfied vs Marital Status.
### DS.Alter<-ggplot(DSJob, aes(x=M.S.D, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Married, Single, Divorced") +  ylab("Satisfied in their Job") + ggtitle("Married, Single and Divorced Research Scientist, Satisfied in their Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### DS.Alter

We can conclude that the male employees in ChemicalRepo are "Medium" to "Highly" satisfied. We are also able to conclude that women who are divorced are less satisfied than single women. Yet married women demonstrate the highest satisfaction rating of all three types of marital statuses. Married women are almost "Highly" satisfied at ChemicalRepo.  When reviewing Research Scientist women are consistent in job satisfaction at a "Medium" to "Highly" satisfied ranking. However, men who are married are closer to "highly satisfied" compared to their respectively lower, single and divorced Research Scientist. 

## Compare Satisfaction in the overall workforce in ChemicalRepo by Yrs between promotion.
## Compare Satisfaction by Research Scientist in ChemicalRepo by Yrs between promotion.

## Total Workforce comparison of Satisfaction vs Years between Promotions.
### Workforce.Promo<-ggplot(Data, aes(x=YbtwnPromo, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Years between Promotions") +  ylab("Satisfied in Job") + ggtitle("Workforce Satisfied Life vs. Years between Promotions") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### Workforce.Promo

## Research Scientist Satisfied vs Years between Promotions. 
### DS.Promo <- ggplot(DSJob, aes(x=YbtwnPromo, y=Satisfied, group=Gender, color=Gender)) +  geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Years between Promotions") +  ylab("Satisfied in Job") + ggtitle("Years between Promotions vs. Satisfaction as a Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### DS.Promo

We can conclude that the employees as a whole in ChemicalRepo are between "Medium" to "Highly" Satisfied in respect to the years between promotions. As to be expected, both women and men become slightly less satisfied in their Jobs the longer they wait between promotions. In review of employees titled as Research Scientist, women become less satisfied at a faster rate than men in years between promotions. Women max out at 10 years between promotion but men continue to wait longer as Research Scientist. This could be due to years of service within the company rather than the candidate being ignored for other reasons.

## Compare Satisfaction in the overall workforce in ChemicalRepo by Income earned per month.
## Compare Satisfaction by Research Scientist in ChemicalRepo by Income earned per month.

## Total Workforce comparison of Satisfaction vs Income per month.
### Workforce.Income<-ggplot(Data, aes(x=Income.mos, y=Satisfied, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method=lm, se=FALSE) + xlab("Income per Month (dollars)") + ylab("Satisfied in their Job") + ggtitle("Workforce Satisfied Life vs. Income per Month") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### Workforce.Income

## Compare income compared to job satisfaction (male vs female).
### DS.Income <- ggplot(DSJob, aes(x=Income.mos, y=Satisfied, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab(" Monthly Income") + ylab("Satisfied in their Job") + ggtitle("Income as a Research Scientist vs. Satisfied Job for Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### DS.Income

We can conclude the employees as a whole in ChemicalRepo are between "Medium" to "Highly" Satisfied with the income or compensation they receive. While men have a slightly higher approval rating in job satisfaction compared to women with respects to income, the difference is marginal.  The results indicate as a Research Scientist, men are paid a higher monthly income overall. The more men are paid the less satisfied they are with work. They start with ranking their satisfaction beyond "Highly Satisfied" but as they increase past $5k a month, it's observed that their job satisfaction drops below that of women. Men who make almost $10k a month rank a "Medium Satisfaction" with the job.  Which is inversed to what most would consider as a normal response to an increase in pay.  We believe this could be contributed to an increase of demands on the male employees who are making more income. However, the more women are paid the more satisfied they are with the work they perform.

## How satisfied are Research Scientist in their job at ChemicalRepo.
### DS.Attrition <- ggplot(DSJob, aes(x=Attrition, y=Satisfied, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab(" Attrition") + ylab("Satisfied in their Job") + ggtitle("Attrition vs. Satisfied Job for Research Scientist") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### DS.Attrition

We can conclude that the Research Scientists that leave the company are still above the medium level of job satisfaction. Women who leave the company were slightly less pleased in their positions than men, yet they generally had the same values when they were employed in the company. We find Women are overall less satisfied in their job as Research Scientists than men. However, they both rank the job satisfaction between a "Medium" to "High" satisfaction. 

## 4.d Looking only at life satisfaction data only for all of the employees in ChemicalRepo.
### library(ggplot2)
### par(las=2)

### Turnover <- ggplot(Data, aes(x=Jobs.Worked, y=Satisfied, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Jobs Worked") + ylab("Satisfied in their Job") + ggtitle("Number of Jobs worked compaired to Satisfied Job") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### Turnover

Results indicate women are happier when they start in the workforce. Women who frequently change employment demonstrate they have a less satisfied work experience. Men however can change the jobs equal to women and maintain the same satisfaction as they did when they took their 1st job.  There is no impact on men in being satisfied with work compared to the number of times men change employment. Overall womenand men share equal satisfaction working when they have changed employer less than 2.5 times. 

## How many former jobs is considered normal in ChemicalRepo?
### Age.Jobs <- ggplot(Data, aes(x=Jobs.Worked, y=Age, group=Gender, color=Gender)) + geom_point(aes(color = Gender)) + stat_smooth(method="lm", se=FALSE) + xlab("Jobs Worked") + ylab("Age") + ggtitle("Number of Jobs worked compaired to Age ") + theme(plot.title = element_text(hjust = 0.5)) + coord_flip()
### Age.Jobs

Results also indicate on average both women and men between the approximate age of 33 to 45 change jobs at almost the same rate. On average both men and women by the age of 40 have changed jobs almost 5 times. When compared to the maximum attrition age between 25 to 35 observed that both men and women in their 30's could be working in their first occupation since graduating. We find the attrition relative to the employee taking their first job in the workforce and to the number of jobs at a young age could be summer or high school jobs, even possibly a work-study or school based job (TA/Tutor/Etc). The lowest attrition rates are found in those over 35, although it is worth noting that the age range 33 to 45 considers up to 8 jobs a normal average. Thus were are able to conclude that there is no apparent risk by this age bracket and this many number of jobs worked.

We recommend to either reduce the sales team to those below the age of 25 or increase it beyond 35 years of age. We also recommend, when hiring, do not hold back from hiring employees with at least 8 jobs before they are 45. We conclude this is normal and can be contributed to jobs held while in high school and college. Overall there is a larger section of men holding employment at ChemicalRepo by 60% of the workforce. We also determine those who live greater than 10 miles from their work are less likely to attrition. In conclusion ChemicalRepo could increase the number of females in their workforce, increase the hiring age beyond 35 years old for new employees and look for employees with a commute greater than 10 miles from the office.  Based off the information given, attrition will with reduce by concentration in this area of adjustments.

## CONCLUSION

We hypothesized sales representatives, age and overall commute distance contributes to attrition within a company. We find there is evidence to conclude the sales representatives, age and commute influence attrition. We have discovered that the longer that an employee works for the company, the more they will earn. We do add ChemicalRepo could increae the income in Female employees and increase the job satisfaction. We also found that an increase in commuting distance to work is a positive relationship, meaning employees who live further from work are generally more satisfied and that those who work furthest from home are most satisfied, and this also held true in the job role of a Research Scientist. 

## sessionInfo()

## R version 3.5.1 (2018-07-02)
## Platform: x86_64-apple-darwin15.6.0 (64-bit)
## Running under: macOS Sierra 10.12.6
##
## Matrix products: default
## BLAS:
/Library/Frameworks/R.framework/Versions/3.5/Resources/lib/libRblas.0.dylib
## LAPACK:
/Library/Frameworks/R.framework/Versions/3.5/Resources/lib/libRlapack.dylib
##
## locale:
## [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8
##
## attached base packages:
## [1] stats graphics grDevices utils datasets methods base
##
## other attached packages:
## [1] ggplot2_3.1.1 plyr_1.8.4 readxl_1.3.1
##
## loaded via a namespace (and not attached):
## [1] Rcpp_1.0.0 bindr_0.1.1 knitr_1.21 magrittr_1.5
## [5] tidyselect_0.2.5 munsell_0.5.0 colorspace_1.3-2 R6_2.3.0
## [9] rlang_0.3.1 stringr_1.3.1 dplyr_0.7.8 tools_3.5.1
## [13] grid_3.5.1 gtable_0.2.0 xfun_0.4 withr_2.1.2
## [17] htmltools_0.3.6 assertthat_0.2.0 yaml_2.2.0 lazyeval_0.2.1
## [21] digest_0.6.18 tibble_1.4.2 crayon_1.3.4 bindrcpp_0.2.2
## [25] purrr_0.3.0 codetools_0.2-15 glue_1.3.0 evaluate_0.12
## [29] rmarkdown_1.11 labeling_0.3 stringi_1.2.4 compiler_3.5.1
## [33] pillar_1.3.1 cellranger_1.1.0 scales_1.0.0 pkgconfig_2.0.2





















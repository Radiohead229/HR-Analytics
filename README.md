# HR-Analytics
## A Data Analysis Project on the Performance trends of Employees of a Company using Excel and Power BI
This Data Analysis Project aims in building an **efficient and powerfull Dashboard on Power BI** for the HR team of a Company to track records of working hour, attendance, performance and leaves (**or Presence Overview**) of all the Employees using **Microsoft Excel and Power BI**.

## Data Sources
The **primary dataset** used for this analysis is the **.xlsx file** named **Attendance Sheet 2022-2023_final** in the dataset folder containing all the details of Employees for different months in different sheets. 

## Tools Used
- Excel [_Analysing the Data_]
- Power BI [_CLeaning the Data,using DAX to make new measures and making the Dashboard_ ]


### Data Analysis Expressions used in Power BI

To find the Total Working days of all Employees (_Exact Data_)
```
Total Working days = 

var totalworkdays = COUNT('Final Combined Data'[Value])

var nonworkdays = CALCULATE(COUNT('Final Combined Data'[Value]), 'Final Combined Data'[Value] in {"WO", "HO"})

RETURN 
totalworkdays-nonworkdays
```

To find the percentage of any record (WFH,SL,etc), example here-
(_not Exact Data_)
```
record % = DIVIDE([recod count],[Present days],0)
```
**here make sure you already have a _record count_ column entry in the measure table**

To make a record count measures column 
```
record count = SUM('Final Combined Data'[record count])
```

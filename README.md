# HR-Analytics
 Our HR Analytics project highlights a balanced gender distribution among our Total Employee, 
 with Number of Employees Due for Promotion on the promotion track, Number of Employees Not Due for Promotion, and key insights in job level distribution, 
 retrenchment, and service status, geographic distribution, education backgrounds, job satisfaction trends, and relevant observations over time, 
 as well as specific job roles with promotion and retrenchment implications.

  
## **1.	Overall Employee Demographics:**

What is the total number of employees in the organization?
How does the gender distribution of employees break down (Male vs. Female)?
How many employees are currently due for promotion, and how many are not?
## **2.	Employee Distribution by Job Level:**

What is the distribution of employees by job level or hierarchy?
Are there any patterns or trends in the distribution across different job levels?
## **3.	Retrenchment and Employment Status:**

How many employees have been retrenched, and how many are currently in service?
Is there a specific time period or trend associated with retrenchment?
## **4.	Employee Distribution by Distance:**

How are employees distributed geographically by distance or location?
Are there any insights related to the location of employees?
## **5.	Employee Distribution by Education Field:**

What are the educational backgrounds of your employees?
Are certain education fields more prevalent among your workforce?
## **6.	Employee Job Satisfaction:**

How satisfied are your employees with their jobs?
Is there any correlation between job satisfaction and other variables, such as job level or education field?
## **7.	Employee Trends Over Time:**

How has the total number of employees changed over time?
Are there any noticeable patterns or trends in employee growth or attrition?
## **8.	Job Roles and Promotion/Retrenchment:**

Which job roles have the highest number of employees due for promotion?
Which job roles have the highest number of employees at risk of retrenchment?
Are there any job roles that overlap, i.e., employees due for promotion and at risk of retrenchment?
![HR Analytics_Actions](https://github.com/SMalhotra563/HR-Analytics/assets/147312244/c13f0ee2-fe2c-44b6-afff-c9c24dc64399)

![HR Analytics_Home](https://github.com/SMalhotra563/HR-Analytics/assets/147312244/6d7d88f8-6c06-4580-885e-a1c380f5947c)

![HR Analytics_Details](https://github.com/SMalhotra563/HR-Analytics/assets/147312244/0049c41d-c34c-4910-bbf5-7ba3c78aba4c)

# DAX Formulas Used in Measures

### For CalculatingTotal Employee:
 **Tota Emp** = COUNTROWS('HR Analytics Data')


### For Calculating Female: 
 **Female** = Calculate([Tota Emp],'HR Analytics Data'[Gender]="Female")
 **% Female** = DIVIDE([Female],[Tota Emp],0)

### For Calculating Male:
 **Male** = CALCULATE([Tota Emp],'HR Analytics Data'[Gender]="male")
 **% male** = DIVIDE([Male],[Tota Emp],0)

### For Calculating the Status of the promotion among Total Employees:

 **Due for promotion** = CALCULATE ([Tota Emp],'HR Analytics Data'[Promotion Status]="Due for promotion")
 **% Due for promotion** = DIVIDE ([Due for promotion],[Tota Emp],0)

 **Not Due for promotion** = CALCULATE ([Tota Emp],'HR Analytics Data'[Promotion Status]="Not Due")
 **% Not Due for promotion** = DIVIDE([Not Due for promotion],[Tota Emp],0)

### For Calculating the Status of the Retrenchment among Total Employees:
 **Will be Retreanched** = IF(ISBLANK(Calculate([Tota Emp],'HR Analytics Data'[Retreachment status]="Will be Retreanched")),0,Calculate([Tota Emp],'HR Analytics Data'[Retreachment status]="Will be Retreanched"))
  **% Will be Retrenched** = DIVIDE([Will be Retrenched],[Tota Emp],0)

 **On Service** = IF(ISBLANK(Calculate([Tota Emp],'HR Analytics Data'[Retreachment status]="On Service")),0,Calculate([Tota Emp],'HR Analytics Data'[Retreachment status]="On Service"))
  **% On Service** = DIVIDE([On Service],[Tota Emp],0)

### For Calculating the Rating among Total Employees:
 **High Rated** = IF(ISBLANK(Calculate([Tota Emp],'HR Analytics Data'[Performance]="High Rating")),0,Calculate([Tota Emp],'HR Analytics Data'[Performance]="High Rating"))
  **% High Rated** = DIVIDE([High Rated],[Tota Emp],0)

 **Low Rated** = IF(ISBLANK(Calculate([Tota Emp],'HR Analytics Data'[Performance]="Low Rating")),0,Calculate([Tota Emp],'HR Analytics Data'[Performance]="Low Rating"))
  **Low Rated**= DIVIDE([Low Rated],[Tota Emp],0)

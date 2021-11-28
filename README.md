# Pewlett-Hackard Employee Analysis

## Retiree Overview
In this analysis, our goal was to highlight the number of retiring employees by title in efforts to find out which employees are eligibile to participate a Mentorship Program.
Instead of having a significant percent of the workforce retiring, management would like to introduce a mentoriship program in which experienced employees will have the
opportunity to return to a part-time role to mentor newly hired individuals. As many employees near their retirement age, it's important to first highlight the number of
retiring employees and then we can later determine who would be eligible to become a mentor.

## Retiring Employee Results

By using SQL and PgAdmin, we were able to look into large subsets of employee data and even combine our datasets into tailored lists for review. We did this in a few steps:

First, we captured all employees and their respective titles from the Employees and Titles tables. We named this new table as Retirement Titles. Within this, we included 
the employee number, the employees first and last name, their title, and their hire and end dates:

![image](https://user-images.githubusercontent.com/89496798/143786209-d172d202-e1c5-4908-b8fb-39339a4807ea.png)

Next, we refactored our code to only include unique titles for each empployee. We named this table Unique Titles. As we know, employees may have transitioned into different roles or departments and in this casse,
we used the most recent job title by ordering our employee number by ascending, and then our to_date by deescnding:

![image](https://user-images.githubusercontent.com/89496798/143786316-5620a20e-d47f-4b2d-a04e-85cb4bd4c00c.png)

After this, we created a table to break down the number of employees per title that are retiring:

![image](https://user-images.githubusercontent.com/89496798/143786362-d2957a04-e234-444e-b8e3-c178a49456c5.png)

Once we narrowed down the lists of employees near retirement, we created a final table to determine who would be eligible to participate in the program. We used data from the
Employees, Department Employees, and Titles tables to compile our list. We used the to_date column and employee birth dates between January 1, 1965 and December 31, 1965 as our filters.
We named this table Mentorship Eligiblity:

![image](https://user-images.githubusercontent.com/89496798/143786477-08a0c705-ec0f-4832-af7f-f771c04e250b.png)

## Silver Tsunami Summary
As we review the data above, it's important to focus on how many employees there are near retirement and how many are eligible for the mentorship program. First, we can find out the number of current employees by couting the employee numbers in our Current Employees table:

![image](https://user-images.githubusercontent.com/89496798/143787046-31c6e76d-ff87-41d1-892f-970910c54c4f.png)

Let's also get the count of employees eligible for the mentorship program:

![image](https://user-images.githubusercontent.com/89496798/143787251-13790f3f-aab8-4af3-85db-56526211d5f0.png)

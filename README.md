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
- The number of employees identified in this list is **133,776**, however, these do include duplicates.

To find unique titles, we refactored our code to only include the most recent title for each empployee. We named this table Unique Titles. As we know, employees may have transitioned into different roles or departments and in this casse,
we used the most recent job title by ordering our employee number by ascending, and then our to_date by descending:

![image](https://user-images.githubusercontent.com/89496798/143786316-5620a20e-d47f-4b2d-a04e-85cb4bd4c00c.png)
- The number of employees with unique titles near retirement is **90,398**. 

After this, we created a table to break down the number of employees per title that are retiring:

![image](https://user-images.githubusercontent.com/89496798/143786362-d2957a04-e234-444e-b8e3-c178a49456c5.png)
- As we can see from above, a majority of employees retiring are Senior Engineers (**29,414**) and Senior Staff (**28,255**).
- Senior Engineers and Senior Staff retiring accounts for **63.80%** of all retiring.

Once we narrowed down the lists of employees near retirement, we created a final table to determine who would be eligible to participate in the program. We used data from the
Employees, Department Employees, and Titles tables to compile our list. We used the to_date column and employee birth dates between January 1, 1965 and December 31, 1965 as our filters.
We named this table Mentorship Eligiblity:

![image](https://user-images.githubusercontent.com/89496798/143786477-08a0c705-ec0f-4832-af7f-f771c04e250b.png)

## Silver Tsunami Summary
As we review the data above, it's important to focus on the count of employees retiring bulletted above vs. the number of those eligible for the mentorship program. We captured the total number of employees retiring by counting the employee number from our unique_titles table:

![image](https://user-images.githubusercontent.com/89496798/143789371-60652089-0305-42ba-bf48-f67d6bd98b74.png)
- This gives us an idea of how many roles will need to be filled as the "silver tsunami" begins to make an impact - **90,398**.

Now, we can also count the number of employees eligible for the mentorship program:

![image](https://user-images.githubusercontent.com/89496798/143789429-4d3a1005-adcb-44fc-9d28-7af7f6cf8875.png)
- This is only **1.72%** of the **90,398** retiring. This is not nearly enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees.

By further breaking down the count of those eligible for the mentorship program by title we can compare this with those retiring with a similar title:

![image](https://user-images.githubusercontent.com/89496798/143789646-f66e56ea-1ae1-4666-aaa4-4b77531bba99.png)

By comparing the two tables:

![image](https://user-images.githubusercontent.com/89496798/143789668-d2ae231b-5151-48a3-bb83-ff0f3753c0c0.png) -- ![image](https://user-images.githubusercontent.com/89496798/143789679-d1bc6880-6242-4522-9be3-1d20b0591338.png)


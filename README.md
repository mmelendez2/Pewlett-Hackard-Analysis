# Pewlett-Hackard Employee Analysis

## Retiree Overview
In this analysis, our goal was to highlight the number of retiring employees by title in efforts to find out which employees are eligible to participate a Mentorship Program.
Instead of having a significant percent of the workforce retiring, management would like to introduce a mentorship program in which experienced employees will have the
opportunity to return to a part-time role to mentor newly hired individuals. As many employees near their retirement age, it's important to first highlight the number of
retiring employees and then we can later determine who would be eligible to become a mentor.

## Retiring Employee Results

By using SQL and PgAdmin, we were able to investigate large subsets of employee data and even combine our datasets into tailored lists for review. We did this in a few steps:

First, we captured all employees and their respective titles from the Employees and Titles tables. We named this new table as Retirement Titles. Within this, we included 
the employee number, the employees first and last name, their title, and their hire and end dates:

![image](https://user-images.githubusercontent.com/89496798/143786209-d172d202-e1c5-4908-b8fb-39339a4807ea.png)
- The number of employees identified in this list is **133,776**, however, these do include duplicates.

To find unique titles, we refactored our code to only include the most recent title for each employee. We named this table Unique Titles. As we know, employees may have transitioned into different roles or departments and in this case, we used the most recent job title by ordering the employee number by ascending, and then the to_date by descending:

![image](https://user-images.githubusercontent.com/89496798/143786316-5620a20e-d47f-4b2d-a04e-85cb4bd4c00c.png)
- The number of employees with unique titles near retirement is **90,398**. 

After this, we created a table to break down the number of employees per title that are retiring:

![image](https://user-images.githubusercontent.com/89496798/143786362-d2957a04-e234-444e-b8e3-c178a49456c5.png)
- As we can see from above, most of the employees retiring are Senior Engineers (**29,414**) and Senior Staff (**28,255**).
- Senior Engineers and Senior Staff retiring accounts for **63.80%** of all retiring.

Once we narrowed down the lists of employees near retirement, we created a final table to determine who would be eligible to participate in the program. We used data from the
Employees, Department Employees, and Titles tables to compile our list. We used the to_date column and employee birth dates between January 1, 1965 and December 31, 1965 as our filters.
We named this table Mentorship Eligibility:

![image](https://user-images.githubusercontent.com/89496798/143786477-08a0c705-ec0f-4832-af7f-f771c04e250b.png)

## Silver Tsunami Summary
As we review the data above, it's important to focus on the count of employees retiring bulleted above vs. the number of those eligible for the mentorship program. We captured the total number of employees retiring by counting the employee number from our unique_titles table:

![image](https://user-images.githubusercontent.com/89496798/143789371-60652089-0305-42ba-bf48-f67d6bd98b74.png)
- This gives us an idea of how many roles will need to be filled as the "silver tsunami" begins to make an impact - **90,398**.

Now, we can also count the number of employees eligible for the mentorship program:

![image](https://user-images.githubusercontent.com/89496798/143789429-4d3a1005-adcb-44fc-9d28-7af7f6cf8875.png)
- This is only **1.72%** of the **90,398** retiring. This is not nearly enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett-Hackard employees.

By further breaking down the count of those eligible for the mentorship program by title we can compare this with those retiring with a similar title:

![image](https://user-images.githubusercontent.com/89496798/143789646-f66e56ea-1ae1-4666-aaa4-4b77531bba99.png)

By comparing the two tables:

![image](https://user-images.githubusercontent.com/89496798/143789751-bb486874-dedf-43c0-8fa0-6f148cf859a7.png)

- There would only be **569** Senior Staff eligible to mentor newly hired Senior Staff needed to fill the **28,255** retiring (**2.01%**)
- There would only be **501** Engineers eligible to mentor newly hired Engineers needed to fill the **14,222** retiring (**3.52%**)
- There would only be **169** Senior Engineers eligible to mentor newly hired Senior Engineers needed to fill the **29,414** retiring (**0.58%**)
- There would only be **155** Staff eligible to mentor newly hired Staff needed to fill the **12,242** retiring (**1.267%**)
- There would only be **78** Assistant Engineers eligible to mentor newly hired Assistant Engineers needed to fill the **1,761** retiring (**4.43%**)
- There would only be **77** Technique Leaders eligible to mentor newly hired Technique Leaders needed to fill the **4,502** retiring (**1.71%**)
- There will **not be any** Managers eligible to train the newly hired Managers needed to fill the **2** retiring (**0.00%**)
 
Given the extremely low percentages of those eligible to mentor within their respective titles and responsibilities, it may be best to create very detailed documentation outlining the responsibilities of their roles at a high level. Those newly hired will have to heavily rely on their immediate teams rather than being mentored. The demand for mentors will be too high to support the influx of new hires. If Pewlett-Hackard does decide to move forward with the mentorship program, it would be wise to only assign mentors to new hires that may be having a hard time with the subject matter or their tasks.

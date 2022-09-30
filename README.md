# Pewlett-Hackard-Analysis
## Overview of the Analysis
Pewlett_Hackard(PH) is facing a "silver tsunami". To rise the challenge, PH company needs to get well prepared. The analysis is target to retiring employees.

The purpose of this analysis is to create two tables: one to determine the number of retiring employees and their position titles, and the other to identify employees who are eligible to participate in a mentorship program. Within the first table, we included information such as employee number, first and last name, position title, and start and end date. In the second, we added employee number, first and last name, birth date, start and end date, and position title.
  
## Results
### The Number of Retiring Employees by Title
- table holds all the titles of employees who were born between 1952 and 1955. Since some of employees has taken different positions in the company, employees' number and name are dupulicate. Table head is shown as below:

![Retirement Titles table](https://user-images.githubusercontent.com/105877888/178130790-120d2fda-a960-42ac-a686-887adf2c0c84.PNG)

 table holds the most recent title of employees from Retirement Titles table. Each employee in the table is unique. Table head is shown as below:

![Unique Titles table](https://user-images.githubusercontent.com/105877888/178130793-32c559eb-9b45-4120-bb92-46572e1f3fe2.PNG)

-  table holds the number of retirement-age employees by their most recent title. The caculation was based on Unique Titles table. Table is shown as below:

![Retiring Titles table](https://user-images.githubusercontent.com/105877888/178130810-6e533cd0-4d54-4a57-8da8-b51af4564507.PNG)

### The Employees Eligible for the Mentorship Program
-  table holds mentorship-eligible employees. These current employees were born in 1965. Table head is shown as below:



## Summary
  - To discover how many roles will need to be filled as the "silver tsunami" begins to make an impact, we summerized the number of employees who are at retirement-age. 
```
SELECT COUNT(emp_no)
FROM unique_titles;
```
Output of the total number of retiring employees from unique_titles table is 72458. This means Pewlett Hackard needs to hire 72458 new employees to fill these positions as the time of older and experienced employees are retired. 
  - The total number of employees from mentorship_eligibility table tells us if there are eough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees. Query is as follows: 
```
SELECT COUNT(emp_no)
FROM mentorship_eligibility;
```
The result returns 1549. This is roughly 1/47 times to the number of retiring employees. 
In order to training new less experienced employees, the ratio of mentors to mentees will be as low as 1:47. Apparently, there will be too much work for mentors and less efficency for mentees. 

*Pewlett Hackard may have some options to overcome the mentor-shortage challenge.*
  1. *Enlarge the age range of mentorship-eligibility from 1965 to 1960~1965. So there will be more professional employees engage in mentorship.*
  2. *Hire experienced employees to shorten mentorship period. Peer mentoring also adoptable. Individuals may knowledgable on different aspect, they can help each other.*
  3. *Act sooner and get well prepared before "silver tsunami" make an impact. Increase recruiting numbers a couple of years earlier can share the mentorship pressure.*
  
    




# Pewlett-Hackard-Analysis
## Overview of the Analysis
Pewlett_Hackard(PH) is facing a "silver tsunami". To rise the challenge, PH company needs to get well prepared. The analysis is target to retiring employees.
  1. Use `INNER JOIN` to combine employees and titles tables. 
     Then retrieve employees' information who were born in 1952 through 1955 and currently working in the company.
  2. Use `DISTINCT ON` and `ORDER BY` to get the retiring employees' current position.
  3. Use `COUNT` and `GROUP BY` to sort and count the retiring employees by department.
  4. Use `INNER JOIN` to retrieve current employees' personal information, who were born in 1965, and their titles. These employees are eligible for mentorship.
  
## Results
### The Number of Retiring Employees by Title
- [Retirement Titles](https://github.com/valentindv97/Pewlett-Hackard-Analysis/blob/main/Data/retirement_titles.csv) table holds all the titles of employees who were born between 1952 and 1955. Since some of employees has taken different positions in the company, employees' number and name are dupulicate. Table head is shown as below:

![Retirement Titles table](https://user-images.githubusercontent.com/105877888/178130790-120d2fda-a960-42ac-a686-887adf2c0c84.PNG)

- [Unique Titles](https://github.com/valentindv97/Pewlett-Hackard-Analysis/blob/main/Data/unique_titles.csv) table holds the most recent title of employees from Retirement Titles table. Each employee in the table is unique. Table head is shown as below:

![Unique Titles table](https://user-images.githubusercontent.com/105877888/178130793-32c559eb-9b45-4120-bb92-46572e1f3fe2.PNG)

- [Retiring Titles](https://github.com/valentindv97/Pewlett-Hackard-Analysis/blob/main/Data/retiring_titles.csv) table holds the number of retirement-age employees by their most recent title. The caculation was based on Unique Titles table. Table is shown as below:

![Retiring Titles table](https://user-images.githubusercontent.com/105877888/178130810-6e533cd0-4d54-4a57-8da8-b51af4564507.PNG)

### The Employees Eligible for the Mentorship Program
- [Mentorship Eligibility](https://github.com/CelineWW/Pewlett-Hackard-Analysis/blob/main/Data/mentorship_eligibility.csv) table holds mentorship-eligible employees. These current employees were born in 1965. Table head is shown as below:

![Mentorship Eligibility table](https://user-images.githubusercontent.com/105877888/178130932-72dc8ca2-daa8-49a7-90c0-9dc120f0fde2.PNG)

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
  
    




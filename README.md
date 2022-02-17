# Pewlett-Hackard-Analysis
# Project overview
    Pewlett-Hackard-Analysis is to understand the number of people who are leaving, hiring or being moved within the company.
# Results
    . We have the empolyees filter by their titles.
    . The employees that are filter by titles, but they have a unique job titles.
    . We have the counts of employee in each titles.
    . Lastly, we have the employees who are eligible for mentorship.
# Summary
  . 90,398 roles are in urgent need to be filled out as soon as the workforce starts retiring at any given time.
  . No, we have 1,940 employees who are eligible to participate in a mentorship program.
  
SELECT DISTINCT ON(e.emp_no) e.emp_no, 
    e.first_name, 
    e.last_name, 
    e.birth_date,
    de.from_date,
    de.to_date,
    t.title
INTO mentorship_eligibilty
FROM employees as e
Left outer Join dept_employee as de
ON (e.emp_no = de.emp_no)
Left outer Join title as t
ON (e.emp_no = t.emp_no)
WHERE (e.birth_date BETWEEN '1965-01-01' AND '1965-12-31')
ORDER BY e.emp_no;
SELECT * FROM mentorship_eligibilty

Dataset Explanation
1. students
 Contains basic student details.
 Key column: student_id
 Purpose: Identifies each student uniquely.

2. courses
 Contains course-related information.
 Key column: course_id
 Purpose: Identifies each course uniquely.

3. enrollments
 Connects students and courses.
 Key columns: student_id, course_id
 Purpose: Stores which student enrolled in which course.

- Relationship Between Tables
One student can enroll in many courses.
One course can have many students.
This creates a many-to-many relationship.
The enrollments table resolves this relationship.

- Logical Links
students.student_id = enrollments.student_id
courses.course_id = enrollments.course_id

- Why JOINs Are Used
Data is stored in multiple tables.
JOINs combine related rows using common columns.
JOINs work by matching values, not by constraints.

Types of JOINs
1. INNER JOIN
Returns only rows where matching values exist in both tables.
 Non-matching rows are excluded from the result.

2. LEFT JOIN
Returns all rows from the left table and matching rows from the right table.
 If no match is found, NULL values appear for right-table columns.

3. RIGHT JOIN
Returns all rows from the right table and matching rows from the left table.
 If no match is found, NULL values appear for left-table columns.

4. FULL JOIN
Returns all rows from both tables.
 Rows without matches show NULL values on the missing side.

5. CROSS JOIN
Returns every possible combination of rows from both tables.
 Result size equals rows in table A multiplied by rows in table B.

6. SELF JOIN
A table is joined with itself using a condition.
 Used to compare rows within the same table.

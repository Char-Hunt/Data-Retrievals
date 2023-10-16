# SQL Query Filtering
## Lab Purpose:

As a security analyst, the ability to make better queries to retrieve specific pieces of data can help you find the security-related information you need more efficiently.
In this lab activity, I applied basic filters to SQL queries to retrieve information from a MariaDB database.
MariaDB is a popular open-source relational database that is compatible with MySQL.
This activity provided me with a great opportunity to apply what I’ve learned and add filters to SQL queries.

>_Note: The terms row and record are used interchangeably in this lab activity and have the same meaning._
## Lab Objective

The objective of this lab was to get specific information about employees, their machines, and their related departments. Me and my team needed this data to perform various tasks, such as running updates, posting privacy notices in certain departments, and sending an alert to an employee with a specific issue on a machine.
As analysts, we are responsible for finding the required information by querying a database. In this scenario, we’ll add filters to your queries to locate the information more quickly.
You might do something like this: First, you will need to list all organization machines and their operating systems. (Once this is determined you can narrow it down.) Second, we’ll list all machines with the operating system OS 2. Third, we’ll list all the employees in the Finance and Sales departments. Fourth, you’ll gather information about the machines.

>_Note: In this lab you’ll be working with the organization database and the tables it contains._
## Task 1. List all organization machines

In this task, we needed to get a list of all organization machines and their operating systems. The data is contained in the machines table. To get the information I used the <code>SELECT</code> keyword to return specific columns.

- Run a SQL query to retrieve only the device_id and operating_system columns from the machines table.
![1545e65r86fiyurs65r86tgouh3_1](https://github.com/Char-Hunt/Data-Retrievals/assets/138831832/10a8958d-d894-43d7-9c44-6ae41841bf66)

How many rows were returned from the machines table? (You can view the number of rows at the bottom of the output.)

   - [x] 200
   - 100
   - 250
   - 300

## Task 2. Retrieve a list of the machines with OS 2

For this task, I found a list of all machines with the 'OS 2' operating system. These machines needed an update. To get this information, you’ll run your first SQL query with a filter.

   - Select all the records from the machines table with a value of 'OS 2' in the operating_system column. Replace the value X with the correct string:

![1545ar6t97ouaf3fgibecb8673_2](https://github.com/Char-Hunt/Data-Retrievals/assets/138831832/5c192095-4281-4900-be15-ab5742dff785)

>_Note: The <code>WHERE</code> clause allows you to filter the results returned by a query by returning only the records that satisfy the condition._
How many machines in the database use the OS 2 operating system?

   - 44
   - 200
   - 88
   - [x] 80

## Task 3. List employees in specific departments

In this task, I pulled a list of all the employees in the Finance and Sales departments to obtain their office numbers. A notice about confidential file handling (in this case financial information) will be posted to those offices. I initially ran into problems isolating the two groups. but after modifiying the WHERE clause I was able to break it down.
Here's how I did this:

   1. Filter the rows returned from the department column in the employees' table to include only employees from the 'Finance' department. Replace X with the appropriate column name and Y with the appropriate value to complete the filter:
![1545b044e75rf8iyfgk703r6t7g_3](https://github.com/Char-Hunt/Data-Retrievals/assets/138831832/dccf37f7-b5fc-4454-b6a2-db17ab9c14fc)

What is the employee_id of the first row returned?

   - 1001
   - [x] 1003
   - 1049
   - 1119

  2. Modify the previous query so that it returns employees who are in the 'Sales' department.
![15457af5t7rfiygkub3r76fg889a_4](https://github.com/Char-Hunt/Data-Retrievals/assets/138831832/cc9eca85-89e5-4f76-a1ab-2be43891a4b3)

How many employees work in the Sales department?

   - 10
   - [x] 33
   - 17
   - 42

## Task 4. Identify employee machines

My team recently discovered issues with machines in the South building. In this task, we needed to retrieve certain employee and computer information.
A machine in 'South-109' has an issue. I needed to determine which employee uses that computer so we could send them an alert.

![154547c586d886rt87tgouhbj2_5](https://github.com/Char-Hunt/Data-Retrievals/assets/138831832/99bc10af-09e4-4aff-8f2a-56498a889d47)

Which of the following employees uses the computer with the issue?

 - jhill
 - [x] jlansky
 - nmitchell
 - tsnow

Next, our team discovered an issue with all the machines in the South building. Offices in the organization have a naming convention using the building name, a hyphen, and the office number in that building (for example, 'South-109').

2. Modify the query you used in the previous step so that it returns information on all the employees in the 'South' building. Use the <code>LIKE</code> operator with <code>%</code> in this query.

>_Note: The <code>LIKE</code> keyword in SQL performs simple string matches. The matching pattern may include the wildcard % to represent a string of any length. This wildcard <code>%</code> may be placed both before and after the targeted substring._

![1545096ce646t97youguiu89c2_6](https://github.com/Char-Hunt/Data-Retrievals/assets/138831832/00b74a70-d6d1-4618-b4e4-880f9f096907)

Which department does the first employee listed in the South building belong to?

  - [x] Finance
  - Marketing
  - Sales
  - Information Technology

## Lessons Learned:

In this lab, we have used basic SQL filtering queries to:

   - Apply the <code>WHERE</code> clause to filter what a SQL query returns and
   - Use the <code>LIKE</code> operator to filter for patterns.

1) | Term       | Meaning                                                                             | Example                   |
| ---------- | ----------------------------------------------------------------------------------- | ------------------------- |
| **App**    | A collection of tools, tabs, objects, and features designed for a specific purpose. | College Management App    |
| **Object** | A database table that stores related information.                                   | Student Object            |
| **Record** | A single row of data inside an object.                                              | One student’s details     |
| **Field**  | A column inside an object that stores specific information.                         | Student Name, Roll Number |
Simple Understanding
App = Complete system
Object = Table
Record = One entry in the table
Field = Information stored in columns
Example

If we create a College Management App:

Objects → Student, Faculty, Course
Fields in Student Object → Name, Roll No, Branch
Record → “Ehalya, 101, CSE”

2) | Standard Objects                        | Custom Objects                       |
| --------------------------------------- | ------------------------------------ |
| Already provided by Salesforce          | Created by users                     |
| Used for common business needs          | Used for organization-specific needs |
| Examples: Account, Contact, Opportunity | Examples: Student, Library, Hostel   |
| Cannot be deleted                       | Can be modified or deleted           |
| Have predefined functionality           | Fully customizable                   |
Example
Standard Object → Contact
Custom Object → Student__c
3)College Data Model
Objects Used
Student
Faculty
Course
Department
Attendance
Relationships
One Department has many Students
One Faculty teaches many Courses
One Student can attend many Courses
Attendance belongs to Student and Course

4) Formula Fields
Formula Fields automatically calculate values based on other fields.
Example 1: Student Full Name
Formula
Full Name=First Name+Last Name\text{Full Name} = \text{First Name} + \text{Last Name}Full Name=First Name+Last Name
Explanation
This formula combines First Name and Last Name automatically.
Example 2: Percentage Calculation
Formula
Percentage=Marks ObtainedTotal Marks×100\text{Percentage} = \frac{\text{Marks Obtained}}{\text{Total Marks}} \times 100Percentage=Total MarksMarks Obtained​×100
Explanation
Used to calculate student percentage automatically whenever marks are entered.
Example 3: Attendance Status
Formula
IF(Attendance_Percentage__c >= 75, "Eligible", "Not Eligible")
Explanation


If attendance is greater than or equal to 75%
Student becomes eligible for exams
Otherwise marked as not eligible

5)  Validation Rules
Validation Rules ensure correct data is entered into the system.
Example 1: Phone Number Validation
Rule
LEN(Phone__c) <> 10
Error Message
“Phone number must contain exactly 10 digits.”
Explanation
Prevents users from entering invalid phone numbers.

Example 2: Age Validation
Rule
Age__c < 17
Error Message
“Student age must be greater than 17.”
Explanation
Ensures only eligible students are admitted.

Example 3: Email Validation
Rule
NOT(CONTAINS(Email__c, "@"))
Error Message
“Enter a valid email address.”
Explanation
Checks whether the email contains “@”.

6)  Reflection: Why Structured Enterprise Data Matters
Structured enterprise data is very important because organizations store large amounts of information every day. Properly organized data helps businesses work efficiently and make better decisions.
Importance of Structured Data
Improves accuracy of information
Reduces duplicate records
Makes searching and reporting easier
Helps in automation and analytics
Increases productivity
Ensures better communication between departments
College Example
In a college system:
Student records are stored properly
Attendance and marks can be tracked easily
Faculty can access course details quickly
Reports can be generated automatically

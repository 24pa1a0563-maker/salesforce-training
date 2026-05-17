1. What is SOQL?

SOQL (Salesforce Object Query Language) is a query language used in Salesforce to retrieve data from objects.
It is similar to SQL, but SOQL is specially designed for Salesforce data.

Using SOQL, we can:

* Read records from objects
* Filter data using conditions
* Retrieve related object data
* Sort and limit records

### Example:

```apex
SELECT Name, Email FROM Contact WHERE City__c = 'Vijayawada'
```

This query retrieves the Name and Email fields from the Contact object where the city is Vijayawada.

 2. What is an Apex Trigger?

An Apex Trigger is a piece of Apex code that executes automatically when certain events happen on Salesforce records.

Triggers help automate business logic when records are:

* Inserted
* Updated
* Deleted
* Restored

Triggers can run:

* Before saving data
* After saving data

 Example:

If a new student record is created, a trigger can automatically:

* Generate a roll number
* Send a welcome email
* Update related records



3. Difference
 Flow vs Trigger

| Flow                            | Trigger                            |
| ------------------------------- | ---------------------------------- |
| Mostly configuration based      | Completely code based              |
| Easier for admins               | Used by developers                 |
| Drag-and-drop automation        | Written in Apex language           |
| Best for simple automation      | Best for complex logic             |
| Less coding knowledge needed    | Programming knowledge required     |
| Limited for advanced operations | Handles advanced operations easily |

Example:

* Flow → Send email when student record is created
* Trigger → Automatically calculate attendance percentage for thousands of records


 Before Trigger vs After Trigger

| Before Trigger                        | After Trigger                      |
| ------------------------------------- | ---------------------------------- |
| Executes before record is saved       | Executes after record is saved     |
| Used to validate or modify data       | Used for related actions           |
| Faster because data not committed yet | Used when record ID is needed      |
| Can change field values directly      | Cannot directly modify same record |

 Example:

* Before Trigger → Set default fee status
* After Trigger → Create related payment record

---

# 4. Your Trigger Use Cases (5 Examples)

## 1. Automatic Roll Number Generation

When a new student record is created, the trigger automatically generates a unique roll number.


2. Attendance Warning System

If attendance percentage falls below 75%, the trigger updates the warning status automatically.


 3. Fee Payment Update

When a payment record is inserted, the trigger changes the student fee status to “Paid”.



4. Library Fine Calculation

When a book return date exceeds the due date, the trigger calculates the fine automatically.

---

## 5. Placement Eligibility Check

If a student’s CGPA becomes greater than 7.0, the trigger marks the student as eligible for placements.


 5. Query Examples (English Query Ideas)
 Example 1

1)English:

Show all students from CSE department.

2)SOQL:

```apex
SELECT Name FROM Student__c WHERE Department__c = 'CSE'
```

 Example 2

1)English:

Get students whose attendance is below 75%.

2) SOQL:

```apex
SELECT Name, Attendance__c 
FROM Student__c 
WHERE Attendance__c < 75
```

Example 3

1) English:

Show all unpaid fee records.

2) SOQL:

```apex
SELECT Name, Fee_Status__c 
FROM Student__c 
WHERE Fee_Status__c = 'Unpaid'
```

Example 4

1) English:

Retrieve top 5 students based on CGPA.

2) SOQL:

```apex
SELECT Name, CGPA__c 
FROM Student__c 
ORDER BY CGPA__c DESC 
LIMIT 5
```
 Example 5

1) English:

Display all books issued to a student.

2)SOQL:

```apex
SELECT Book_Name__c 
FROM Library_Record__c 
WHERE Student__c = 'Student Id'
```

6. Reflection – Why Enterprise Systems React Automatically to Data Changes

Enterprise systems contain large amounts of data and many users work on the same system simultaneously.
Manual monitoring of every change is difficult and time-consuming.

Automatic reactions using Flows and Triggers help organizations:

* Reduce manual work
* Improve accuracy
* Maintain data consistency
* Save time
* Enforce business rules instantly

For example, in a college management system:

* Fee status updates automatically after payment
* Attendance warnings are generated instantly
* Placement eligibility changes automatically based on CGPA

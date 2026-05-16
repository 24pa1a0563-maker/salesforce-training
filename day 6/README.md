 1. What is SOQL?

SOQL (Salesforce Object Query Language) is a query language used in Salesforce to retrieve data from objects.
It is similar to SQL, but SOQL is specially designed for Salesforce data.

Using SOQL, we can:

* Read records from Salesforce objects
* Filter data using conditions
* Retrieve related object data
* Sort and limit records

Example

```apex
SELECT Name, Email FROM Contact WHERE City = 'Vijayawada'
```

This query fetches:

* Contact Name
* Contact Email
  where the city is Vijayawada.

2. What is an Apex Trigger?

An **Apex Trigger** is a piece of Apex code that executes automatically when data changes occur in Salesforce.

Triggers run:

* Before or after inserting records
* Before or after updating records
* Before or after deleting records

Triggers help automate business logic inside enterprise applications.

 Example

If a student record is created:

* Automatically generate Student ID
* Send notification to admin
* Update department statistics

 3. Difference
1) Flow vs Trigger

| Flow                              | Apex Trigger               |
| --------------------------------- | -------------------------- |
| Low-code automation tool          | Code-based automation      |
| Easy to build using drag-and-drop | Requires Apex programming  |
| Best for simple automation        | Best for complex logic     |
| Faster development                | More flexible and powerful |
| Used by admins                    | Used by developers         |

Example

* **Flow:** Send welcome email after student registration.
* **Trigger:** Prevent duplicate roll numbers using advanced validation logic.
2) Before Trigger vs After Trigger

| Before Trigger                      | After Trigger                                |
| ----------------------------------- | -------------------------------------------- |
| Runs before saving data             | Runs after saving data                       |
| Used to validate or modify data     | Used for actions after save                  |
| Faster because no extra save needed | Used when record ID is required              |
| Example: update field values        | Example: send email or create related record |

 Example

### Before Trigger

```apex
trigger StudentBeforeInsert on Student__c (before insert) {
    for(Student__c s : Trigger.new){
        s.Status__c = 'Active';
    }
}
```
 After Trigger

```apex
trigger StudentAfterInsert on Student__c (after insert) {
    for(Student__c s : Trigger.new){
        System.debug('Student Created: ' + s.Name);
    }
}
```
 4. Your Trigger Use Cases (5 Examples)

 1. Automatic Student ID Generation

When a new student record is created:

* Trigger generates a unique Student ID automatically.

---

 2. Attendance Warning

If attendance percentage becomes less than 75%:

* Trigger updates warning status automatically.

---

 3. Fee Due Alert

When fee payment date expires:

* Trigger sends reminder notification to student.


 4. Course Capacity Validation

Before enrolling a student:

* Trigger checks whether seats are available.

---

## 5. Library Fine Calculation

After returning a book:

* Trigger calculates late fine automatically.


5. Query Examples (English Query Ideas)

| English Requirement                               | SOQL Query                                                    |
| ------------------------------------------------- | ------------------------------------------------------------- |
| Show all students from CSE department             | `SELECT Name FROM Student__c WHERE Department__c='CSE'`       |
| Find students with pending fees                   | `SELECT Name FROM Student__c WHERE Fee_Status__c='Pending'`   |
| Display faculty with more than 5 years experience | `SELECT Name FROM Faculty__c WHERE Experience__c > 5`         |
| Show books currently unavailable                  | `SELECT Name FROM Library_Book__c WHERE Available__c = false` |
| Find students with attendance below 75%           | `SELECT Name FROM Student__c WHERE Attendance__c < 75`        |


 6. Reflection — Why Enterprise Systems React Automatically to Data Changes

Modern enterprise systems handle thousands of records every day.
Manual checking and updating is slow and error-prone.

Automatic reactions using Flows and Triggers help organizations:

* Save time
* Reduce human mistakes
* Maintain accurate data
* Improve productivity
* Enforce business rules instantly

For example, in a college management system:

* Fee reminders,
* attendance alerts,
* seat validation,
* and student ID generation

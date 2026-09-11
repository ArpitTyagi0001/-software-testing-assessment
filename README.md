Assessment Test – Software Tester (QA)

Full Name: Arpit Tyagi

Email ID:  arpittyagi389@gmail.com

Contact Number: 8445970389


1. Test Scenarios and Test Cases



A. Registration

Test Case


REG-01


Scenario : Register with valid name, email and password

Expected Result : User should be registered successfully


REG-02


Scenario : Register with an already registered email

Expected Result : System should show an appropriate error


REG-03


Scenario : Submit registration form with all fields empty

Expected Result : Required field validation should be displayed


REG-04


Scenario : Enter invalid email format

Expected Result : System should show invalid email message


REG-05


Scenario : Enter password less than minimum length

Expected Result : Password validation should be displayed


REG-06


Scenario : Enter password and confirm password differently

Expected Result : System should show password mismatch error


REG-07


Scenario : Enter maximum allowed characters

Expected Result : System should accept the data if within the limit


REG-08


Scenario : Enter more than the allowed characters

Expected Result :  should show validation message


REG-09


Scenario : Enter special characters in input fields

Expected Result : System should handle them correctly


REG-10 


Enter spaces only in required fields

Expected Result : User should remain logged in if the session is valid


B. Login


Test Case



LOGIN-01


Scenario : Login with valid email and password

Expected Result : User should login successfully


LOGIN-02


Scenario : Login with wrong password


Expected Result : Error message should be displayed



LOGIN-03


Scenario : Login with unregistered email

Expected Result : Login should fail with proper message


LOGIN-04


Scenario :  Leave email empty

Expected Result : Email validation should be displayed


LOGIN-05


Scenario :  Leave password empty

Expected Result : Password validation should be displayed


LOGIN-06


Scenario :  Enter invalid email format

Expected Result : Validation message should be displayed


LOGIN-07

Scenario :  Enter wrong credentials multiple times

Expected Result : System should handle repeated failed attempts properly


LOGIN-08

Scenario :  Check password field

Expected Result : Password should be masked


LOGIN-09

Scenario :  Logout and try to open task page

Expected Result : User should be redirected to login


LOGIN-10

Scenario :  Refresh page after login

Expected Result : User should remain logged in if the session is valid


2. Task CRUD Operations

Create Task


Test Case

Expected Result


CREATE-01

Scenario : Create a task with valid information

Expected Result :Task should be created successfully


CREATE-02


Scenario : Create task without entering required title

Expected Result :Validation message should be shown


CREATE-03

Scenario :  Enter only spaces as task title

Expected Result :Task should not be created


CREATE-04


Scenario :  Enter maximum allowed title length

Expected Result :Task should be created successfully


CREATE-05

Scenario :  Enter more than maximum allowed length

Expected Result :Validation message should be displayed


CREATE-06


Scenario :  Create two tasks with same name

Expected Result :System should handle duplicate tasks correctly


CREATE-07


Scenario :  Click Create button multiple times quickly

Expected Result :Duplicate tasks should not be created


CREATE-08

Scenario :  Refresh after creating task

Expected Result : Created task should still be available



View Task List


Test Case


VIEW-01

Scenario : Open task list when tasks are available

Expected Result : All user’s tasks should be displayed


VIEW-02


Scenario : Open task list when there are no tasks

Expected Result : Proper empty-state message should be displayed


VIEW-03

Scenario : Create multiple tasks and check list

Expected Result : All tasks should be displayed correctly


VIEW-04


Scenario : Refresh the task list

Expected Result : Tasks should remain consistent


VIEW-05

Scenario : Try to view another user’s task

Expected Result : User should not be able to access it


Edit Task


Test Case



EDIT-01


Scenario : Edit task with valid information

Expected Result : Task should be updated successfully


EDIT-02


Scenario : Edit task and leave required field empty

Expected Result : Validation message should be displayed


EDIT-03


Scenario : Edit task with maximum allowed data

Expected Result : Task should save successfully


EDIT-04

Scenario : Cancel editing

Expected Result : Original task should remain unchanged


EDIT-05


Scenario : Edit another user’s task

Expected Result : User should not be allowed to edit it


EDIT-06

Scenario : Refresh after editing

Expected Result : Updated information should remain saved


Delete Task

Test Case


DELETE-01


Scenario : Delete an existing task

Expected Result : Task should be deleted successfully


DELETE-02


Scenario : Click Delete and cancel confirmation

Expected Result :Task should remain


DELETE-03


Scenario : Click Delete and confirm

Expected Result : Task should be removed


DELETE-04


Scenario : Refresh after deletion

Expected Result : Deleted task should not come back


DELETE-05


Scenario : Try to delete another user’s task

Expected Result : User should not be allowed to delete it


DELETE-06

Scenario : Click Delete multiple times

Expected Result : Application should handle the request correctly

3. Input Validation and Error Handling

I would check the following:

* Required fields should not accept empty values.
* Spaces-only values should be rejected.
* Email should have a valid format.
* Password should follow the defined password rules.
* Maximum field length should be properly handled.
* Special characters should not break the application.
* HTML/JavaScript input should not execute.
* SQL injection type input should be handled safely.
* Server or database errors should show a proper user-friendly message.
* Technical error details or database information should not be shown to users.
* If the internet/server connection fails, the application should handle it properly.
* Clicking the same button multiple times should not create duplicate records.
* User should not be able to access another user’s tasks.
* After logout, protected task pages should not be accessible.

4. Potential Bugs / Risk Areas

Bug 1

Description: A user can view another user’s tasks by changing the task ID.
Severity: Critical
Reason/Impact: This is a security and privacy issue because users should only see their own tasks.

Bug 2

Description: Passwords are stored without proper encryption/hashing.
Severity: Critical
Reason/Impact: If the database is compromised, user passwords could be exposed.

Bug 3

Description: SQL injection can be performed through login or task fields.
Severity: Critical
Reason/Impact: An attacker may access or modify database information.

Bug 4

Description: Clicking the Create button twice creates two identical tasks.
Severity: Major
Reason/Impact: It can create duplicate and incorrect task data.

Bug 5

Description: A task appears deleted on the screen but comes back after refreshing.
Severity: Major
Reason/Impact: The UI and database may not be synchronized correctly.

Bug 6

Description: Edit shows a success message but the updated task is not actually saved.
Severity: Major
Reason/Impact: The user may think their information was saved when it was not.

Bug 7

Description: Very long task names break the page or cause an error.
Severity: Major
Reason/Impact: Boundary values are not handled properly and can affect application stability.

Bug 8

Description: Server/database errors display technical error messages or stack traces.
Severity: Major
Reason/Impact: This gives users a poor experience and may expose sensitive technical information.

Bug 9

Description: User can still access the task page after logging out by using the browser back button or direct URL.
Severity: Critical
Reason/Impact: Unauthorized users may access protected information.

Bug 10

Description: Registration accepts the same email address multiple times.
Severity: Major
Reason/Impact: It can create duplicate user accounts and cause login/account-management problems.

5. Testing Approach

Since the application is close to production and there is no existing test documentation, I would first test the most important functionality.

My priority would be:

1. Registration and Login
2. Authentication and user access
3. Create, View, Edit and Delete tasks
4. Database data persistence
5. Input validation
6. Error handling
7. Security-related scenarios
8. Boundary and negative testing
9. Basic usability and performance testing
10. Regression testing after fixing bugs

I would make sure that the main user flow works correctly:

Register → Login → Create Task → View Task → Edit Task → Delete Task → Logout

Before production release, I would especially focus on security, data loss, unauthorized access and the core CRUD functionality because these can have a high impact on users.

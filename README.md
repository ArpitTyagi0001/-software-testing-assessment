Assessment Test – Software Tester (QA)

Full Name: Arpit Tyagi
Email ID:  arpit.tyagi.cse.2023@miet.ac.in
Contact Number: 8445970389
1. Test Scenarios and Test Cases

A. Registration

Test Case

Scenario

Expected Result

REG-01

Register with valid name, email and password

User should be registered successfully

REG-02

Register with an already registered email

System should show an appropriate error

REG-03

Submit registration form with all fields empty

Required field validation should be displayed

REG-04

Enter invalid email format

System should show invalid email message

REG-05

Enter password less than minimum length

Password validation should be displayed

REG-06

Enter password and confirm password differently

System should show password mismatch error

REG-07

Enter maximum allowed characters

System should accept the data if within the limit

REG-08

Enter more than the allowed characters

System should show validation message

REG-09

Enter special characters in input fields

System should handle them correctly

REG-10 
Enter spaces only in required fields

B. Login

Test Case

Scenario

Expected Result

LOGIN-01

Login with valid email and password

User should login successfully

LOGIN-02

Login with wrong password

Error message should be displayed

LOGIN-03

Login with unregistered email

Login should fail with proper message

LOGIN-04

Leave email empty

Email validation should be displayed

LOGIN-05

Leave password empty

Password validation should be displayed

LOGIN-06

Enter invalid email format

Validation message should be displayed

LOGIN-07

Enter wrong credentials multiple times

System should handle repeated failed attempts properly

LOGIN-08

Check password field

Password should be masked

LOGIN-09

Logout and try to open task page

User should be redirected to login

LOGIN-10

Refresh page after login

User should remain logged in if the session is valid

2. Task CRUD Operations

Create Task

Test Case

Scenario

Expected Result

CREATE-01

Create a task with valid information

Task should be created successfully

CREATE-02

Create task without entering required title

Validation message should be shown

CREATE-03

Enter only spaces as task title

Task should not be created

CREATE-04

Enter maximum allowed title length

Task should be created successfully

CREATE-05

Enter more than maximum allowed length

Validation message should be displayed

CREATE-06

Create two tasks with same name

System should handle duplicate tasks correctly

CREATE-07

Click Create button multiple times quickly

Duplicate tasks should not be created

CREATE-08

Refresh after creating task

Created task should still be available

View Task List

Test Case

Scenario

Expected Result

VIEW-01

Open task list when tasks are available

All user’s tasks should be displayed

VIEW-02

Open task list when there are no tasks

Proper empty-state message should be displayed

VIEW-03

Create multiple tasks and check list

All tasks should be displayed correctly

VIEW-04

Refresh the task list

Tasks should remain consistent

VIEW-05

Try to view another user’s task

User should not be able to access it

Edit Task

Test Case

Scenario

Expected Result

EDIT-01

Edit task with valid information

Task should be updated successfully

EDIT-02

Edit task and leave required field empty

Validation message should be displayed

EDIT-03

Edit task with maximum allowed data

Task should save successfully

EDIT-04

Cancel editing

Original task should remain unchanged

EDIT-05

Edit another user’s task

User should not be allowed to edit it

EDIT-06

Refresh after editing

Updated information should remain saved

Delete Task

Test Case

Scenario

Expected Result

DELETE-01

Delete an existing task

Task should be deleted successfully

DELETE-02

Click Delete and cancel confirmation

Task should remain

DELETE-03

Click Delete and confirm

Task should be removed

DELETE-04

Refresh after deletion

Deleted task should not come back

DELETE-05

Try to delete another user’s task

User should not be allowed to delete it

DELETE-06

Click Delete multiple times

Application should handle the request correctly

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

# Test Cases

## Test Case 1: Verify adding a new employee with valid input values

- **Priority**: High
- **Preconditions**: The user is logged in with an HR account.

### Steps

| Step | Test Steps                                 | Test Data             | Expected Results                                           |
|------|--------------------------------------------|-----------------------|------------------------------------------------------------|
| 1    | Click on the Employee section from the sidebar. | /                     | Employee section is displayed.                            |
| 2    | Click on the "+ Add Employee" button.      | /                     | User is redirected to “Add Employee” page.                |
| 3    | Fill in the Name field: "Miki"             | "Miki"                | The "Name" field displays "Miki". The avatar field shows a circle with "M" inside it. |
| 4    | Fill in the Surname field: "Maus"           | "Maus"                | The "Surname" field displays "Maus". The avatar field shows a circle with "MM" inside it. |
| 5    | Fill in the Email field: "miki.maus@gmail.com" | "miki.maus@gmail.com" | The "Email" field displays "miki.maus@gmail.com".         |
| 6    | Select the Location option: "Niš"          | “Niš”                 | The “Niš” option is selected.                             |
| 7    | Select the Tier option: "Benefiti Test 500" | “Benefiti Test 500”   | The “Benefiti Test 500” option is selected.               |
| 8    | Click on the "Save" button.                | /                     | User is redirected to the “Employees” page. The new employee "Miki Maus" is added to the list of employees. A notification appears stating "Employee successfully created!". |

## Test Case 2: Verify editing an employee's details

- **Priority**: High
- **Preconditions**: 
  - The user is logged in with an HR account.
  - There is at least one employee in the list with a Tier “Benefiti Test 500”.

### Steps

| Step | Test Steps                                     | Test Data              | Expected Results                                           |
|------|------------------------------------------------|------------------------|------------------------------------------------------------|
| 1    | Click on the Employee section from the sidebar. | /                      | Employee section is displayed.                            |
| 2    | Click on the search bar                       | /                      | The employee(s) is/are displayed and visible in the list. |
| 3    | Enter the employee’s name                     | Employee from the precondition | Employee’s name is displayed in the search bar. Additional employees may be displayed if their names/emails contain the employee’s name. |
| 4    | Click on the kebab menu located on the right side of the employee's row. | /                      | A dropdown menu appears with options. When hovering over an option, it darkens to indicate it is selectable. |
| 5    | Click on “Edit”.                              | /                      | User is redirected to “Edit Employee” page.               |
| 6    | Scroll down to the "Tier" field.               | /                      | The "Tier" field becomes visible on the screen.           |
| 7    | Change the employee's tier from "Benefiti Test 500" to "Benefiti Test 300". | “Benefiti Test 300”    | The new tier "Benefiti Test 300" is selected in the tier field. |
| 8    | Click on the "Update" button.                 | /                      | User is redirected to the Employees page. Green notification appears with text “Employee successfully edited!”. Employee’s Tier field contains updated value “Benefiti Test 300”. |

## Test Case 3: Verify employee status changed after clicking on verification link sent by HR

- **Priority**: High
- **Preconditions**: 
  - The user is logged in with an HR account.
  - There is at least one non-verified employee in the list (indicated by a red cross in the "Verified" column).

### Steps

| Step | Test Steps                                    | Test Data                       | Expected Results                                           |
|------|-----------------------------------------------|---------------------------------|------------------------------------------------------------|
| 1    | Click on the Employee section from the sidebar. | /                               | Employee section is displayed.                            |
| 2    | Click on the search bar                       | /                               | The employee(s) is/are displayed and visible in the list. |
| 3    | Enter the employee’s name                     | Employee from the precondition   | Employee’s name is displayed in the search bar. There is also a red cross icon in the column “Verified”. |
| 4    | Click on the kebab menu located on the right side of the employee's row. | /                               | A dropdown menu appears with options. When hovering over an option, it darkens to indicate it is selectable. |
| 5    | Click on “Resend Verification Link”.          | /                               | User stays on the same page. Green notification appears with text “Verification link successfully sent”. The employee's status remains non-verified until the employee completes the verification process. |
| 6    | Open the email from a non-verified employee.   | /                               | The email with subject “Benefiti - Please verify your email” is present. |
| 7    | Click on the “Verify Email” button from the mail. | /                               | User is redirected to the Set password page. The Email field is filled with employee’s email. New Password and Confirm Password fields are empty. |
| 8    | Enter required data and click on “Set Password” button | “test1234”                     | User is redirected to login page.                         |
| 9    | Login with the HR account.                     | /                               | The employee's status indicator changes to a green check mark in the "Verified" column. |
| 10   | Click on the Employee section from the sidebar. | /                               | Dashboard page is displayed.                              |
| 11   | Click on the search bar                       | /                               | The employee(s) is/are displayed and visible in the list. |
| 12   | Enter the employee’s name                     | Employee from the precondition   | Employee’s name is displayed in the search bar. There is also a green check mark icon in the column “Verified”. |

## Test Case 4: Delete an employee immediately (using today’s date)

- **Priority**: High
- **Preconditions**: 
  - The user is logged in with an HR account.
  - There is at least one employee present in the list.

### Steps

| Step | Test Steps                                    | Test Data                | Expected Results                                           |
|------|-----------------------------------------------|--------------------------|------------------------------------------------------------|
| 1    | Click on the Employee section from the sidebar. | /                        | Employee section is displayed.                            |
| 2    | Click on the search bar                       | /                        | The employee(s) is/are displayed and visible in the list. |
| 3    | Enter the employee’s name                     | Employee from the precondition | Employee’s name is displayed in the search bar. Additional employees may be displayed if their names/emails contain the employee’s name. |
| 4    | Click on the kebab menu located on the right side of the employee's row. | /                        | A dropdown menu appears with options. When hovering over an option, it darkens to indicate it is selectable. |
| 5    | Click on “Delete”.                            | /                        | A modal window titled "Disable User" appears.             |
| 6    | Click on the date field within the modal.     | /                        | A calendar widget appears.                               |
| 7    | Select today's date.                         | /                        | The calendar widget closes. The selected date is displayed in the date field. |
| 8    | Click the "Submit" button in the modal.       | /                        | The modal closes, a green notification appears with text “User disabled!”, and the employee is no longer listed in the employee table. |

## Test Case 5: Verify the behavior of the search functionality when the search input field is left empty

- **Priority**: Medium
- **Preconditions**: 
  - The user is logged in with an HR account.
  - There is at least one employee present in the list (preferably more).

### Steps

| Step | Test Steps                                    | Test Data | Expected Results                                       |
|------|-----------------------------------------------|-----------|--------------------------------------------------------|
| 1    | Click on the Employee section from the sidebar. | /         | Employee section is displayed.                        |
| 2    | Click on the search bar                       | /         | The employee(s) is/are displayed and visible in the list. |
| 3    | Leave the search field empty and press "Enter." | /         | The results stayed the same.                          |

## Test Case 6: Verify the behavior of the search functionality when the search input field contains only one character

- **Priority**: Medium
- **Preconditions**: 
  - The user is logged in with an HR account.
  - There is at least one employee present in the list (preferably more) whose name/lastname/email contains the character “ž”.

### Steps

| Step | Test Steps                                    | Test Data | Expected Results                                       |
|------|-----------------------------------------------|-----------|--------------------------------------------------------|
| 1    | Click on the Employee section from the sidebar. | /         | Employee section is displayed.                        |
| 2    | Click on the search bar                       | /         | The employee(s) is/are displayed and visible in the list. |
| 3    | Enter a single character into the search bar and press "Enter." | “ž”       | The application returns a list of employees whose names/emails contain the character "ž". |
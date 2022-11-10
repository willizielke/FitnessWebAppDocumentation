# 1 Use-Case Name
Create operation

## 1.1 Brief Description
Every normal user can create new operations, making him the organizer of the newly created operation. An organizer must provide a good deal of information about the upcoming operation, like

- required ressources (must have, optional)
- the public and the private description of the operation
- the place/location
- the date and time the operation takes place 

The information can be split into a public and a private part. The private part can only be seen by accepted team members.

# 2 Flow of Events
## 2.1 Basic Flow
- User clicks on "create operation" button
- User fills in the the form
- User clicks on "create" to create the operation, he will be sent to the details view of the operation. A success message will be shown.
- User clicks on "cancel" to close the form without saving the operation.

### 2.1.1 Activity Diagram
![Organization Application Activity Diagram](../Diagrams/UCs/CreateOperationActivityDiagramm.jpg)

### 2.1.2 Mock-up
![Create Operation Form Wireframe](../Pictures/Wireframes/CreateOperation.png)

### 2.1.3 Narrative
```gherkin
Feature: new operation

  As a signed in user
  i want to create a new operation
  and provide additional information regarding my intentions
  in order to find willing helpers.

  Background:
    And I am on the homepage

  Scenario: open new operation dialog
    Given I am signed in with username "USER" and password "PASSWORD"
    And I am on the "main" page
    When I press the "new operation" button
    Then I am on the "new operation" page

  Scenario: enter valid data and save the operation
    Given I am signed in with username "USER" and password "PASSWORD"
    And I am on the "new operation" page
    When I enter "operation XY" in the field "title"
    And I enter "Karlsruhe" in the field "location"
    And I enter "01.01.2018" in the field "date"
    And I enter "public description" in the field "public_descripion"
    And I enter "private description" in the field "private_description"
    And I press the "save" button
    Then I am on the "details" page
    And I receive a "success" message

  Scenario: enter invalid data and save the operation
    Given I am signed in with username "USER" and password "PASSWORD"
    And I am on the "new operation" page
    When I enter "operation XY" in the field "title"
    And I enter "Karlsruhe" in the field "location"
    And I enter "no date" in the field "date"
    And I enter "" in the field "public_descripion"
    And I enter "" in the field "private_description"
    And I press the "save" button
    Then I am on the "new operation" page
    And I receive a "error" message
```

## 2.2 Alternative Flows
(n/a)

# 3 Special Requirements
(n/a)

# 4 Preconditions
## 4.1 Login
The user has to be logged in to the system.

# 5 Postconditions
(n/a)
 
# 6 Extension Points
(n/a)

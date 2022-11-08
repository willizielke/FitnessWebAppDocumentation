# 1 Use-Case Name

Start Excercise

## 1.1 Brief Description

The user should be able to start their exercises.
The user has to click "Start" to start the exercise timer. 
The user can pause the excercise. 
After the excercise is finished the next excercise will be shown.
If the user stops the excercise, the current workoutplan will be shown.


# 2 Flow of Events

## 2.1 Basic Flow
- User clicks on "Start" to start the exercise and the active time.
- User clicks on "Pause" to pause the exercise, stops the active time and starts the pause countdown time.
- User clicks on "Continue" to continue the next repetition or to go to the next exercise
- User clicks on "Stop" to stop the excercise and go to workoutplan view


### 2.1.1 Activity Diagram

![Activity Diagram "Start Workout"](../ActivityDiagrams/Start_Exercise.drawio.svg)

### 2.1.2 Mock-up

![Mock-up "Start Workout"](../MockUps/MockUpStartExercise.drawio.svg)

### 2.1.3 Narrative


```gherkin
Feature: Start Exercise

  As a signed in user
  i want to start, pause and stop an exercise of a "Workoutplan"

  Background:
    Given I am signed in with username "USER" and password "PASSWORD"
    And I am on the "Workout" page
    And I started a "Workoutplan"
    And the exercise window is visible

  Scenario: Start the exercise
    Given the timer is set to "0:00"
    And the "Start" button is visible
    When I press the "Start" button
    Then the "Timer" starts counting up

  Scenario: Pause the excercise
    Given the "Timer" is counting up
    And there are more "Repetitions" of the exercise
    And the "Pause" button is visible
    When I press the "Pause" button
    Then the time of the "Timer" is saved
    And the "Timer" is set to a "Pause" time
    And the "Timer" starts counting down

  Scenario: Add 20s to pause time
    Given the "Timer" is counting down
    And the "+20s" button is visible
    When I press the "+20s" button
    Then the "Timer" adds 20 seconds to the time

  Scenario: Continue the exercise
    Given the "Timer" is counting down
    And the "Continue" button is visible
    When I press the "Continue" button or the "Timer" is set to "0:00"
    Then the time of the "Timer" is set to "0:00"
    And the "Timer" starts counting up

  Scenario: Continue with the next exercise
    Given the "Timer" is counting up
    And the "Save and Continue with next Exercise" button is visible
    And there is a next exercise
    When I press the "Save and Continue with next Exercise" button
    Then the time of the "Timer" is saved
    And the "Timer" stops counting
    And the "Timer" is set to a "0:00" time
    And the the next exercise is visible

  Scenario: Workoutplan finished
    Given the "Timer" is counting up
    And the "Finish" button is visible
    And there is no next exercise
    When I press the "Finish" button
    Then the time of the "Timer" is saved
    And I am on the "Workoutplan" page
    And the current workoutplan is visible

  Scenario: Stop the excercise
    When I press the "Stop" button
    Then the exercise window is closed
    And I am on the "Workoutplan" page
    And the current workoutplan is visible
```

## 2.2 Alternative Flows

(n/a)

# 3 Special Requirements

(n/a)

# 4 Preconditions

The user has to be logged in to the system.
The user has to have navigated to the workout site

# 5 Postconditions

(n/a)

# 6 Extension Points

(n/a)

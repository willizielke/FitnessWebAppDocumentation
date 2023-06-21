# 1 Use-Case Name

Calculate Bmi and Calories

## 1.1 Brief Description

Every normal user can calculate his BMI and Caloric Intake based on his gender, age, weight, height and physical actitvity.

- Enter Age, Weight, Height and choose Gender and Physical Activity
- Get BMI and Calories

# 2 Flow of Events

## 2.1 Basic Flow

- User chooses his gender
- User enters his age
- User enters his weight
- User enters his height
- User chooses his physical activity

### 2.1.1 Activity Diagram

![Calculate BMI and Calories](../ActivityDiagrams/Calculate_Bmi_And_Calories.drawio.svg)

### 2.1.2 Mock-up

![Calculate BMI and Calories](../MockUps/MockUpCalculateBMIAndCalories.drawio.svg)

### 2.1.3 Narrative

```gherkin
Feature: calculate bmi and calories

  As a signed in user
  i want to calculate my bmi and calories

  Background:
    Given I am signed in with username "USER" and password "PASSWORD"
    And I am on the bmi page

  Scenario: enter valid data and calculate bmi and calories
    When I choose "male" in the field "gender"
    And I press the "next" button
    And I enter "22" in the field "age"
    And I press the "next" button
    And I enter "85" in the field "weight"
    And I press the "next" button
    And I enter "181" in the field "height"
    And I press the "next" button
    And I choose "Low Activity" in the field "physical activity"
    And I press the "next" button
    Then I receive a "Your Calories are 2788, Your BMI is 25.95 and you are Overweight" message
```

## 2.2 Alternative Flows

(n/a)

# 3 Special Requirements

(n/a)

# 4 Preconditions

## 4.1 Login

The user has to be logged in to the system.
The user has to have navigated to the BMI page

# 5 Postconditions

(n/a)

# 6 Extension Points

(n/a)

---
title: Assignment 1
---
# Assignment 1: Iterative Programming Practice
In this assignment, you will write a very simple iterative robot program that prints diagnostic messages to the console.
## Requirements
1. When the robot turns on, print `"Robot Has Initialized"` to the console
2. Every cycle of the robot's loop (every time `robotPeriodic()` is called), print the number of times `robotPeriodic()` has been called to the console. For example, the first time you call `robotPeriodic()`, it should print `"1"`, the second time it should print `"2"`, etc.
3. Whenever the robot is enabled in autonomous, print `"Starting Autonomous"` to the console
4. Whenever the robot is enabled in teleop, print `"Starting Teleop"` to the console
5. Every cycle of the robot loop during autonomous (every time `autonomousPeriodic()` is called), print the number of times the robot has entered autonomos (the number of times `autonomousInit()` has been called, then a comma, then the number of times `autonomousPeriodic()` has been called since the robot was most recently enabled into autonomous. For example, if you have called `autonomousInit()` once so far, the first time you call `autonomousPeriodic()` the robot should print `"1,1"` to the console, the second time it should print `"1,2"`, etc. If you have called `autonomousInit()` twice so far, the first time you call `autonomousPeriodic()` the robot should print `"2,1"` to the console, the second time it should print `"2,2"`, etc. Note that the second number should reset to 1 every time you call `autonomousPeriodic()`.
6. Do the equivalent of the requirement above, but for Teleop

## Instructions
* Accept the GitHub Classroom Assignment here: [https://classroom.github.com/a/ytAxq_3W](https://classroom.github.com/a/ytAxq_3W)
* Clone the repository that is created and open it in VSCode. The name of the repository should be `technocrats-programming-training/iterativeprogrammingpractice-<YOUR GITHUB USERNAME>`
* To complete this assignment, you only have to change the file `src/main/java/frc/robot/Robot.java`. Inside this file, you have to edit the following methods
  * `robotInit()`
  * `robotPeriodic()`
  * `autonomousInit()`
  * `autonomousPeriodic()`
  * `teleopInit()`
  * `teleopPeriodic()`
* You should NOT change `disabledInit()` ,`disabledPeriodic()`, `testInit()`, `testPeriodic()`, or any file other than `src/main/java/frc/robot/Robot.java`
* In addition to editing the methods listed above, you will also have to create several instance variables in the class `Robot`. You can initialize them in `robotInit()` (Do not create a constructor). The key to this assignment is storing the number of times different methods have been called as instance variables. You cannot use local variables for this, because they are destroyed and recreated each time you call a method, so their data does not persist between method calls.
* This assignment comes with unit tests to check your work. To run these tests, open a terminal in VSCode and run the command `./gradlew test`. In the output, you should see which tests passed and which tests failed. There is a breakdown of each test in the tests section of this document.

## Tests
Column Explanations:
* Requirement: number from the requirement list above
* Methods Tested: whether the test passes or fails only depends on how you wrote the methods in this box, and your instance variables.

| Test Name | Description | Requirement | Methods Tested |
|---|---|---|---|
|testRobotInitPrints|Checks that `robotInit()` prints `"Robot Has Initialized"`|1|`robotInit()`|
|testRobotPeriodicPrintsNumberOfCalls|Checks that `robotPeriodic()` prints the number of times it has been called|2|`robotPeriodic()`|
|testAutonomousInitPrints|Checks that `autonomousInit()` prints `Starting Autonomous`|3|`autonomousInit()`|
|testTeleopInitPrints|Checks that `teleopInit()` prints `Starting Teleop`|4|`teleopInit()`|
|testAutonomousPeriodicPrintsNumberOfCalls|Checks that `autonomousPeriodic()` prints `"x,y"` if x is the number of times `autonomousInit()` has been called and y is the number of times `autonomousPeriodic()` has been called|5|`autonomousInit()`, `autonomousPeriodic()`|
|testTeleopPeriodicPrintsNumberOfCalls|Checks that `teleopPeriodic()` prints `"x,y"` if x is the number of times `teleopInit()` has been called and y is the number of times `teleopPeriodic()` has been called|6|`teleopInit()`, `teleopPeriodic()`|

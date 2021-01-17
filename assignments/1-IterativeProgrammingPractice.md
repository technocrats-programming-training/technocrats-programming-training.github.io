---
title: Assignment 1
---
# Assignment 1: Iterative Programming Practice
In this assignment, you will write a very simple iterative robot program that prints diagnostic messages to the console.
## Requirements
* When the robot turns on, print `"Robot Has Initialized"` to the console
* Every cycle of the robot's loop (every time `robotPeriodic()` is called), print the number of times `robotPeriodic()` has been called to the console. For example, the first time you call `robotPeriodic()`, it should print `"1"`, the second time it should print `"2"`, etc.
* Whenever the robot is enabled in autonomous, print `"Starting Autonomous"` to the console
* Every cycle of the robot loop during autonomous (every time `autonomousPeriodic()` is called), print the number of times the robot has entered autonomos (the number of times `autonomousInit()` has been called, then a comma, then the number of times `autonomousPeriodic()` has been called since the robot was most recently enabled into autonomous. For example, if you have called `autonomousInit()` once so far, the first time you call `autonomousPeriodic()` the robot should print `"1,1"` to the console, the second time it should print `"1,2"`, etc. If you have called `autonomousInit()` twice so far, the first time you call `autonomousPeriodic()` the robot should print `"2,1"` to the console, the second time it should print `"2,2"`, etc. Note that the second number should reset to 1 every time you call `autonomousPeriodic()`.
* Do the equivalent of the requirement above, but for Teleop

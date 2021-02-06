---
title: Assignment 3
---
# Assignment 3: Simple Single Motor Subsystem
In this assignment, write a robot program capable of using button input to control a simple single motor subsystem (intake, feed, launcher, etc)
## Requirements
1. When the A button on XBoxController 0 is held, set the motor to 0.25 percent output forwards
2. When the B button on XBoxController 0 is held, set the motor to 0.25 percent output backwards
3. When the X button on XBoxController 0 is held, set the motor to 0.5 percent output forwards
4. When the Y button on XBoxController 0 is held, set the motor to 0.5 percent output backwards

## Instructions
* Accept the GitHub Classroom Assignment here: [https://classroom.github.com/a/ua43KTuI](https://classroom.github.com/a/ua43KTuI)
* Clone the repository that is created and open it in VSCode. The name of the repository should be `technocrats-programming-training/iterativeprogrammingpractice-<YOUR GITHUB USERNAME>`
* To complete this assignment, you only have to change the file `src/main/java/frc/robot/Robot.java`. Inside this file, you have to edit the following methods
  * `robotInit()`
  * `teleopPeriodic()`
* You should NOT change any other method in `Robot`, or any file other than `src/main/java/frc/robot/Robot.java`
* In addition to editing the methods listed above, you will also have to create several fields in the class `Robot`. You can initialize them in `robotInit()` (Do not create a constructor). These fields should contain objects for the motor controllers and XBox controller.
* This assignment does not contain unit tests, but you can check that your code compiles using the command `.\gradlew build`

## Feedback
This assignment does not allow for easy unit testing, so there are no unit tests. I will give you feedback by commenting on each commit, which GitHub will automatically turn into a pull request.

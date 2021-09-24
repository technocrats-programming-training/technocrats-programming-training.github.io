---
title: Assignment 2
---
# Assignment 2: Simple Iterative Drivetrain
In this assignment, write a robot program capable of using joystick input to drive a differential drivetrain during teleop.
## Requirements
1. Read 2 axis from the joysticks to determine speed for each side of the drivetrain.
2. Periodically set the motor controllers to the speeds determined from the joysticks.
    * Motor Controller CAN IDs: Drivetrain left side: 1, 2, Drivetrain right side: 3, 4
3. When Button 0 on Joystick 0 is pressed, set the maximum speed of the drivetrain to 0.5 (from this point divide all speeds by 2 before passing them onto the Joysticks.
## Instructions
* Accept the GitHub Classroom Assignment here: [https://classroom.github.com/a/Mt2A5Vit](https://classroom.github.com/a/Mt2A5Vit)
* Clone the repository that is created and open it in VSCode. The name of the repository should be `technocrats-programming-training/iterativeprogrammingpractice-<YOUR GITHUB USERNAME>`
* To complete this assignment, you only have to change the file `src/main/java/frc/robot/Robot.java`. Inside this file, you have to edit the following methods
  * `robotInit()`
  * `teleopPeriodic()`
* You should NOT change any other method in `Robot`, or any file other than `src/main/java/frc/robot/Robot.java`
* In addition to editing the methods listed above, you will also have to create several fields in the class `Robot`. You can initialize them in `robotInit()` (Do not create a constructor). These fields should contain objects for the motor controllers and XBox controller.
* This assignment does not contain unit tests, but you can check that your code compiles using the command `.\gradlew build`

## Feedback
This assignment does not allow for easy unit testing, so there are no unit tests. I will give you feedback by commenting on each commit, which GitHub will automatically turn into a pull request.

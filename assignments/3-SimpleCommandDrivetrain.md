---
title: Assignment 3
---
# Assignment 3: Simple Command Based Drivetrain
In this assignment, write a robot program capable of using joystick input to drive a differential drivetrain during teleop. We will also create a simple autonomous routine that drives the robot forward for a set period of time
## Requirements
TELEOP:

1. Read 2 axis from the joysticks to determine speed for each side of the drivetrain.
2. Periodically set the `Spark` motor controllers to the speeds determined from the joysticks. 
    * Left motor PWM port: 0
    * Right motor PWM port: 1

AUTO:

3. Drive forward at 0.5 speed for 5 seconds

## Instructions
* Accept the GitHub Classroom Assignment here: [https://classroom.github.com/a/BNct7cXt](https://classroom.github.com/a/BNct7cXt)
* Clone the repository that is created and open it in VSCode. The name of the repository should be `technocrats-programming-training/command-based-drivetrain-<YOUR GITHUB USERNAME>`
* To complete this assignment, you will need to edit the following files:
    * `DriveSubsystem.java`:
        * Add `Spark` motors as instance variables (2 total, one for each side of the drivetrain)
        * Add a `public void drive(double left, double right)` method that accepts to `double`s and sets the motors to those speeds
    * `JoystickDriveCommand.java`:
        * Constructor: Initialize the `subsystem` and `controller` instance variables to the `subsystem` and `contorller` parameters. Add `subsystem` to the command's requirements.
        * Edit the `execute()` method to take axis values from the controller and pass them to `subsystem.drive()`
    * `TimedDriveCommand.java`:
        * Add the instance variable `double startTime`
        * Constructor: Initialize the `subsystem` instance variable to the `subsystem` parameter. Add `subsystem` to the command's requirements.
        * Edit the `initialize()` method to set `startTime` to the current time
        * Edit the `execute()` method to call `subsystem.drive(0.5, 0.5)` to constantly drive forward at half speed
        * Edit the `isFinished()` method to check for the time elapsed, and return true if more than 5 seconds has passed. (compare current time to `startTime`)
    * `RobotContainer.java`:
        * Edit the constructor to set `driveSubsystem`'s default command to `joystickDriveCommand`
## Reference
Here are some useful classes and methods, and their import statements
* `Spark` (motor controller class)
    * `import edu.wpi.first.wpilibj.Spark;`
    * Constructor takes integer PWM port number as an argument
    *  `set()` method takes a double percent output speed between -1.0 and  1.0.
*  `getFPGATimestamp()` (returns time since robot boot in seconds)
    * `import static edu.wpi.first.wpilibj.Timer.*;`
* `XboxController` (class representing an XboxController)
    * `import static edu.wpi.first.wpilibj.GenericHID.Hand`
    * `import edu.wpi.first.wpilibj.XboxController`
    *  Use method `getY(Hand.kLeft)` or `getY(Hand.kRight)` to get the state of the  left or right Y axis joystick. These methods return `double`s between -1.0 and 1.0


## Feedback
This assignment does not allow for easy unit testing, so there are no unit tests. I will give you feedback by commenting on each commit, which GitHub will automatically turn into a pull request.

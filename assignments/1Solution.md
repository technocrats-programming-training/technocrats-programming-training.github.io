## Solution
``` java
// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

package frc.robot;

import edu.wpi.first.wpilibj.TimedRobot;
import edu.wpi.first.wpilibj.smartdashboard.SendableChooser;
import edu.wpi.first.wpilibj.smartdashboard.SmartDashboard;

/**
 * The VM is configured to automatically run this class, and to call the functions corresponding to
 * each mode, as described in the TimedRobot documentation. If you change the name of this class or
 * the package after creating this project, you must also update the build.gradle file in the
 * project.
 */
public class Robot extends TimedRobot {

  int periodicAuton; // Field that stores the number of times autonomousPeriodic() has been called since the last autonomousInit()
  int periodicTeleop; // Field that stores the number of times teleopPeriodic() has been called since the last teleopInit()
  int initAuton; // Field that stores the number of times autonomousInit() has been called
  int initTeleop; // Field that stores the number of times teleopInit() has been called
  int robotPeriodic; // Field that stores the number of times robotPeriodic() has been called
  /**
   * This function is run when the robot is first started up and should be used for any
   * initialization code.
   */
  @Override
  public void robotInit() {
    System.out.println("Robot Has Initialized"); // Prints Robot Has Initialized to the screen
    // Set all fields to 0 when the robot turns on.
    this.periodicAuton = 0;
    this.periodicTeleop = 0;
    this.initAuton = 0;
    this.initTeleop = 0;
    this.robotPeriodic = 0;
  }

  /**
   * This function is called every robot packet, no matter the mode. Use this for items like
   * diagnostics that you want ran during disabled, autonomous, teleoperated and test.
   *
   * <p>This runs after the mode specific periodic functions, but before LiveWindow and
   * SmartDashboard integrated updating.
   */
  @Override
  public void robotPeriodic() {
    this.robotPeriodic = this.robotPeriodic + 1; // Increases robotPeriodic by one because robotPeriodic() has been called
    System.out.println(this.robotPeriodic); // Prints the number of times robotPeriodic has been called to the screen
  }

  /**
   * This autonomous (along with the chooser code above) shows how to select between different
   * autonomous modes using the dashboard. The sendable chooser code works with the Java
   * SmartDashboard. If you prefer the LabVIEW Dashboard, remove all of the chooser code and
   * uncomment the getString line to get the auto name from the text box below the Gyro
   *
   * <p>You can add additional auto modes by adding additional comparisons to the switch structure
   * below with additional strings. If using the SendableChooser make sure to add them to the
   * chooser code above as well.
   */
  @Override
  public void autonomousInit() {
    System.out.println("Starting Autonomous"); // Prints Starting Autonomous to the screen
    this.initAuton = this.initAuton + 1; // Increases initAuton by one because autonomousInit() has been called
    this.periodicAuton = 0; // Sets periodicAuton to zero because it is supposed to count the number of times autonmousPeriodic has been called since the last time autonomousInit() has been called, so it must reset to zero every time autonomousInit() is called.
  }

  /** This function is called periodically during autonomous. */
  @Override
  public void autonomousPeriodic() {
    this.periodicAuton = this.periodicAuton + 1; // Increases periodicAuton by one because autonomousPeriodic() has been called
    System.out.println(this.initAuton+","+this.periodicAuton); // Prints initAuton (the number of times autonomousInit() has been called), then a comma, then periodicAuton (the number of times autonomousPeriodic has been called).
  }

  /** This function is called once when teleop is enabled. */
  @Override
  public void teleopInit() { // Analogous to autonomousInit()
    System.out.println("Starting Teleop");
    this.initTeleop = this.initTeleop + 1;
    this.periodicTeleop = 0;
  }

  /** This function is called periodically during operator control. */
  @Override
  public void teleopPeriodic() { // Analogous to autonomousPeriodic()
    this.periodicTeleop++;
    System.out.println(this.initTeleop+","+this.periodicTeleop);
  }

  /** This function is called once when the robot is disabled. */
  @Override
  public void disabledInit() {}

  /** This function is called periodically when disabled. */
  @Override
  public void disabledPeriodic() {}

  /** This function is called once when test mode is enabled. */
  @Override
  public void testInit() {}

  /** This function is called periodically during test mode. */
  @Override
  public void testPeriodic() {}
}
```

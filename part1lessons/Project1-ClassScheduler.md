# Project 1: Class Scheduler
In this project, we will build a simple command line application that manages a 4 block class schedule, and allows the user to edit the schedule.

## Objective
When the user runs the application, the following should happen:
* The program prompts the user for the number of classes to add to the class database. (`How many classes would you like to add?`)
* The program prompts the user for the block, name, and teacher of each class that the user wants to add.
    * *If the answer to the first prompt was 3, the program would prompt `Block: `, `Name: `, `Teacher: ` three times*
* The program will now enter an infinite loop. Each iteration of the loop, the program will prompt the user to enter a command from four options (`Enter a command (add, drop, viewSchedule, viewAvailable):`). Depending on the command entered, the program will perform one of the following tasks: (If anything but `add`, `drop`, `viewSchedule`, or `viewAvailable` is entered, the program should give the command prompt again)
    * `add`: The program will ask the user for a class id (`Enter class ID:`), then add the class with that ID to the schedule. If the block of the class being added is already full, the program should print `Block <block number> is already full.`
    * `drop`: The program will ask the user for a block number (integer between 1 and 4, inclusive) (`Enter block:`), then remove the class with that block from the schedule
    * `viewSchedule`: The program will print out a representation of the current schedule with blocks and class names, printing empty if there is no class in a particular block. Example:
        ```
        Block 1: AP Lang
        Block 2: empty
        Block 3: empty
        Block 4: AP Chem
        ```
    * `viewAvailable`: The program will list all classes from the class database (inputted when the program started). Example:
        ```
        ID: 0, Block: 1, Name: AP Lang, Teacher: Homberger
        ID: 1, Block: 2, Name: AP Physics, Teacher: Ditty
        ID: 2, Block: 3, Name: AP Chemistry, Teacher: Kappel
        ID: 3, Block: 4, Name: HPAL, Teacher: Brueske
        ```

## Instructions
* You will start with an empty gradle project containing four empty classes: `App`, `Schedule`, `Database`, and `Class`
* Start by making a copy of [this](https://docs.google.com/spreadsheets/d/1o6iK2-TGUAl9hpWBud50Jc_IgKeVRerXLaIaeeOC_Oc/edit?usp=sharing) planning document and working out what functions and instance variables you will put in the `App`, `Schedule`, `Database`, and `Class` classes.
* Accept the GitHub classroom assignment [here](https://classroom.github.com/a/SzY1FWUI)
* To run your code, execute `./gradlew run --console=plain -x test` in the shell
* To test your code, execute `./gradlew test` in the shell. For details on what each test does, see the table below

## Tests
| Name | Description |
| ---- | ----------- |
| `testPrintsDatabase` | Starts the program, enters classes into the database, and views available classes to ensure that they match |and views the schedule to ensure that it was added
| `testAddsOneBlock` | Starts the program, enters classes into the database, adds a class to block 1, and views the schedule to ensure that it was added | 
| `testAddsTwoBlocks` | Starts the program, enters classes into the database, adds a class to block 1, adds a class to block 2, and views the schedule to ensure that it was added | 
| `testAddsConflictingBlocks` | Starts the program, enters classes into the database, adds a class to block 2, attempts to add another class to block 2, checks that the `Block 2 is already full` message is printed, and views the schedule to ensure that only the first class added appears |
| `testDrop` | Starts the program, enters classes into the database, adds a class to block 1, adds a class to block 2, drops the class in block 2, and views the schedule to ensure that it was dropped | 
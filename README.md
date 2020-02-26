# Embedded-Systems-Lab-3
Watchdog timer-driven ISR with general I/O

This program is meant to test the reaction speed of the user.

The program will display a message on the serial monitor of the Arduino IDE
  telling the user to enter a decimal number 0-15. The program then displays
  the user's input back to the user in hexadecimal on the screen and on a
  seven-segment LED display.

The watchdog timer in this program is set to run an ISR
  (interrupt service routine) after 4 seconds, where the two dots in the
  middle of the LED (the colon) blink for a 0.5s on/ 0.5s off cycle for
  5 cycles. After the blinking cycles, the Arduino resets.


Lab document below:

ECE 487/587 Spring 2020
Laboratory 3 – Introduction to Watchdog Timers

1.	Introduction
This particular laboratory exercise is designed to introduce you to the use of watchdog timers and reaction timers.  

2.	Requirements
In addition to your Arduino platform and computer, you will also need the following for this lab:
•	Solderless breadboard
•	1k ohm resistor(s) (other resistor values can also work)
•	Wires for use with breadboard
•	Seven-segment display (common anode or common cathode types can be used)

3.	Laboratory Tasks
You are to create a new application that will execute on your Arduino platform.  Your application will begin by querying the user for an integer input (in decimal) from the keyboard.  The valid user input range is 0 – 15. The user has 4 seconds to enter his/her input, and if the input is provided within that 4 second timeout period, the user input should be echoed back to the screen via the serial monitor in hexadecimal, and it should also be displayed on a 7-segment LED in hexadecimal.  The reaction time for the user to provide the input should also be displayed on the serial monitor. The user reaction time is the time from the displaying of the prompt to the time the user provides his/her input. Reaction time resolution should be 1 ms and it should be displayed using this format: “reaction time = x.yyy” where x is the number of seconds and yyy is the number of ms. 

For the user input, all hexadecimal digits must be supported (0-9, A, B, C, D, E, and F).  Upper or lowercase characters are allowed, but the designer should consider consistency, readability, and ways to distinguish between numbers and characters.  The 7-segment LED should have only the middle horizontal segment lit upon initialization after reset or power up.  The LED will stay in this state until the user enters his/her first input.  

The application continuously repeats, asking for an input and displaying that input on the serial monitor and the 7-segment LED, and displaying the reaction time.  If the user does not provide input within 4 seconds of the prompt being displayed, the application should clear the 7-segment LED, blink only the decimal point of the 7-segment LED for 5 seconds (0.5 seconds on and 0.5 seconds off, repeat for 5 seconds total) and display a message on the serial monitor indicating a timeout has occurred.  After the five second blinking period has expired, the application should reset the Arduino board and begin again.   During the 5 second blinking period, all user input should be completely ignored. 

If the user provides invalid data during the 4 second interval when data can be entered, the 7-segment LED should display 3 horizontal lines to indicate that the user input was invalid and an error message should be printed to the screen.  Invalid data should restart the watchdog timer and not lead to a board reset (i.e. invalid input data is still input). However, if invalid data is provided, the reaction time should not be displayed.

4.	Grading
Due Date:  02/21/2020
No late assignments will be accepted.  This is an individual assignment.

All students must demo/explain their project in the lab (SERC 2005) to the TA, Ben Sawyer, by the deadline.  The assignment will be graded at the time of the demo.  There will be no re-submissions (for each lab attempt), so all debugging is the responsibility of the student (the TA doesn’t have time to help you debug your code!).  Each student will have to sign up for a grading/demo time, and the assigned time is the grading/demo time! No exceptions. Arrive a few minutes early to get set up and get ready for your demo time to begin. We want to stay on schedule, so be ready to go when your time starts. If you miss your demo time, you will receive a grade of zero for the lab attempt, and you will have to resubmit. The signup sheet will be posted in SERC 2005 the week before the lab is due. The TA will schedule all grading activities according to the signup sheet. The TA is not able to schedule independent times outside of those posted on the signup sheet. 

You must turn in a hardcopy of your program during your demo with the grading sheet attached as page 1.  The hardcopy of your code should match the code that is being executed!  If it does not match, your grade for the lab will be zero.  Your code should have a header comment indicating your name, CWID, lab assignment, and other pertinent info. I encourage you to verify that your printed code preserves your formatting. Only your printout will be considered for the “programming practices” grade.  

I encourage all students to PLAN AHEAD regarding deadlines.  Deadlines are LIMITS not GOALS! All students should plan to get their assignments done with time to spare to avoid missing the deadline and to get a demo time.  You may need to be flexible when trying to get a demo time. Deadlines are judged based upon when the assignment is demoed (i.e. graded), not when a student says he/she is finished.  If the assignment is not graded by the deadline, it will not be accepted and the student will receive a zero for that lab attempt.  

Grading Guidelines that will be used for Lab #3:
Good Programming Practices:
1)	Comments
2)	Indentation
3)	Good/meaningful variable names
4)	Minimum/wise usage of global variables; unnecessary use of variables
5)	Inefficient code

Grade Breakdown:
30 pts – Good programming practices
70 pts – Functionality/Description of the code



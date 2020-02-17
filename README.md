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

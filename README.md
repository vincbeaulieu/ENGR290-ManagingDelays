# ENGR290-ManagingDelays
Since many students are facing the same issues and struggling with code performance, I've decided to create a short tutorial on delay management.

## Things to consider:  
- The built-in delay() function use Timer_0 to completely halt the program for a given time [[1]].  
- The millis() counts the interrupts generated by Timer_0 overflowing [1].  
- The interrupt priority on Timers are set to be: Timer_2 > Timer_1 > Timer_0 [2].  
- millis is "unsigned long" [3].

[1]: https://forum.arduino.cc/t/problem-enabling-timer0-impacts-general-digital-io-toggle-rate-arduino-uno/676869/4  
[2]: https://forum.arduino.cc/t/which-timer-used-on-mega-for-delay-and-delaymicroseconds/420641/5  
[3]: https://learn.sparkfun.com/tutorials/data-types-in-arduino/all  

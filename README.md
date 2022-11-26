# ENGR290-ManagingDelays
Since many students are facing the same issues and struggling with code performance, I've decided to create a short tutorial on delay management.

## Things to consider:  
- The millis() counts the number of interrupt generated by Timer_0 overflowing [[1]].  
- The built-in delay() function use millis() to completely halt the program for a given time [[2]].  
- millis is "unsigned long" [[3]].

[1]: https://forum.arduino.cc/t/problem-enabling-timer0-impacts-general-digital-io-toggle-rate-arduino-uno/676869/4  
[2]: https://forum.arduino.cc/t/which-timer-used-on-mega-for-delay-and-delaymicroseconds/420641/2
[3]: https://learn.sparkfun.com/tutorials/data-types-in-arduino/all  

## The Problem:
Delay() acts like a wait function. Below I've provided a delay function which directly use millis()
```C++
// Avoid using Delay or Wait when possible
void wait(unsigned long delay){
    unsigned long previous_time = millis(); // Save the current time
    while(millis() < previous_time + delay); // Wait until time has elapsed
}
```

When executed, the above code will save the current_time from millis(), into the variable named *previous_time*. Then, a while loop will execute nothing, as long as the condition *current_time < previous_time + delay* is true.

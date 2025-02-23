TimerThree Library
==================

_Note:_ This fork allows specification of PWM on time in microseconds, rather
than a duty cycle as a proportion of this period. Useful for producing timing
accurate hardware generated pulse trains of specified pulse duration, and
variable frequency.

With the already existing handling of the timer prescaler, a wide range of
periods is available, down to sub-Hz frequencies.

Example of usage for specification of PWM on time:

```c
#define PIN 5
#define ON_TIME_US 40000UL // pulse on time is 40 ms

//initialise timer with 1s period
Timer3.initialize(1000000);

// specify on time
Timer3.pwm_ontime(PIN,ON_TIME_US);
```

These improvements have currently only been made to the AVR portion of the
code, so this is likely only useful on a Mega, Teensy 2.0, Atmega32u4 etc.

---

Paul Stoffregen's modified TimerThree.  This version provides 2 main benefits:

1. Optimized inline functions - much faster for the most common usage
2. Support for more boards

http://www.pjrc.com/teensy/td_libs_TimerOne.html  
https://github.com/PaulStoffregen/TimerThree

Original code

http://playground.arduino.cc/Code/Timer1

Open Source License

TimerThree is free software. You can redistribute it and/or modify it under
the terms of Creative Commons Attribution 3.0 United States License.
To view a copy of this license, visit

http://creativecommons.org/licenses/by/3.0/us/

Paul Stoffregen forked this version from an early copy of TimerOne/TimerThree
which was licensed "Creative Commons Attribution 3.0" and has maintained
the original "CC BY 3.0 US" license terms.

Other, separately developed updates to TimerOne have been released by other
authors under the GNU GPLv2 license.  Multiple copies of this library, bearing
the same name but distributed under different license terms, is unfortunately
confusing.  This copy, with nearly all the code redesigned as inline functions,
is provided under the "CC BY 3.0 US" license terms.

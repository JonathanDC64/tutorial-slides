class: center, middle

# SOEN 422
## Tutorial 1

---

# Agenda

1. Introduction

2. Installing Arduino IDE and Teensyduino

3. Basics of Arduino Programming (What you need to know for Lab 1...)

---

# Introduction

* My name is Patrick

* Best way to contact me is at patrick.ayoup@gmail.com

  * I usually reply very quickly to emails.

* Final Year Student in Software Engineering

* This course is really fun!

---

# Installing Arduino IDE and Teensyduino

* Download and install the [Arduino IDE](http://www.arduino.cc/en/Main/Software) for your operating system. The current latest version is 1.0.5.

  * The Arduino IDE is written in Java. You may need to install the [JRE](http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) if it is not already installed on your workstation.

  * Installation instructions are found [here](http://arduino.cc/en/Guide/HomePage)

* Teensy is an Arduino Compatible development board. Since it is not manufactured by Arduino, some middleware is necessary for loading code onto the device.

* Download and install [Teensyduino](https://www.pjrc.com/teensy/td_download.html) for your operating system.

* Verify that your development environment works by following the instructions on the [Teensy website](https://www.pjrc.com/teensy/tutorial.html) for loading and running the "Blink" program.

---

# Introduction to Arduino

* Arduino programs (called sketches) are written in C or C++.

* The Arduino platform is set of high level C++ libraries used to abstract the details of programming microprocessors.

* Additionally, a small framework is provided to manage the control flow of the sketch execution.

---

# Anatomy of an Arduino Sketch

* A sketch is structured into two functions: ``setup()`` and ``loop()``.

* At the beginning of the sketch's execution, the ``setup()`` function is called once.

  * This is an ideal place to put initialization code.

```c++
void setup() {                
  pinMode(led, OUTPUT);     
}
```

* After calling the ``setup()`` function, the ``loop()`` function is executed as the body of an infinite loop.

```c++
void loop() {
  digitalWrite(led, HIGH);
  delay(1000);
  digitalWrite(led, LOW);
  delay(1000);
}
```

---

# Anatomy of an Arduino Sketch

* Finally, constants and variables should be declared at the top of the sketch.

```c++
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.
 
  This example code is in the public domain.
 */
 
int led = 13; // or #define led 13

void setup() {                
  pinMode(led, OUTPUT);     
}

void loop() {
  digitalWrite(led, HIGH);
  delay(1000);
  digitalWrite(led, LOW);
  delay(1000);
}
```
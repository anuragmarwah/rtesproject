# rtesproject
This repository is for my graduate course project at NYU in the subject Real-Time Embedded System.

## Overview
- This is a team project and the member names are given below:
  - Damian Dziedzic (dsd280@nyu.edu),
  - Anurag Marwah (am8482@nyu.edu),
  - Parth Shah (ps3627@nyu.edu), and 
  - Bolei Zhang (bz824@nyu.edu)
- The duration of the project is from April 2018 to mid-May 2018.

## Description of the Project
- The objective of the project is to design a bot that traverses a minefield.
- The mines will be emitting a sinusoidal audio signal. The set of frequencies will be known beforehand.
- The requirement is to reach the Finish point (which will also be emitting an audio signal of a known frequency), without colliding with any of the mines.

### Specifications of the Bot
- The Bot: <a href="https://www.amazon.com/FEETECH-FT-MC-002-SMC-Aluminum-Vehicle-FT-SMC-2CH/dp/B06XZC2XDV/ref=sr_1_2?ie=UTF8&qid=1524430830&sr=8-2&keywords=ft-smc-2ch"> Amazon Link </a>
- The Microphone: <a href="https://www.amazon.com/WINGONEER-MAX9814-Electret-Microphone-Amplifier/dp/B077XB5Y4X/ref=sr_1_5?ie=UTF8&qid=1524430967&sr=8-5&keywords=mic+module"> Amazon Link </a>
- The Controller: <a href="https://www.amazon.com/Teensy-3-2-with-pins/dp/B015QUPO5Y/ref=sr_1_2?ie=UTF8&qid=1524431163&sr=8-2&keywords=teensy+3.2"> Amazon Link </a>

### The Principle
- Audio input is received through the microphone to the microcontroller ADC
  - It is then processed through a Fast-Fourier Transform to get a spectrum of the frequencies being received and their respective magnitudes
- Based on the frequencies received, a decision is made on the motion of the bot, and accordingly a signal is provided to drive the two PWM Servo Motors
  - It involves moving forward towards the highest magnitude of frequency received
  - Then, stopping at a point of threshold so as to avoid collision
  - And then, re-scanning for more available frequencies
- This is repeated till the bot reaches the finish beacon, where it indicates the completion of task by lighting an LED

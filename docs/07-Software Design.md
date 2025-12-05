Software Design
---

## Introduction
**Team 211** is proposing a solution for households' aquaponics systems. With sensors and actuators, the aim is to integrate smart technology into these systems to allow the user a more stress-free and autonomous experience. To allow a system like this to run, the team chose to utilize **_MPLab IDE_** to send code through the **_Microchip PIC Nano_**. The system runs off of a hub and spoke system, so their is a central board that talks to the other 3 boards, which allow a smooth code and purpose for each board. 

## Research Questions
* Will the code be intuitive enough for any user to utilize the features? 
* Will using the programming software MPLab be sufficient for our team's setup?
* How will the code handle all the functions, and for how long?

## Software Diagram
![TeamLogicFlowChart](image/TeamFlowChartV3.png) **Figure 1:** Program Process   |
[PDF Download](pdf/TeamFlowChartV3.pdf)  |
[Draw.io Download](image/TeamFlowChartV3.xml) |<br>



## Software design V2
Our software functioned fine for the project, it did everything it was meant to do fairly quickly with no major errors. However there are still a few possible improvements that could be made. One possible improvement is the use of interrupts, in our current code each step happens in a linear order, meaning we are limited by every delay in every step. With interrupts we could run the user input logic loop, and have interrupts set up for reading measurement data from the other boards. This could allow us to display measurement data faster as the code would not have to wait through each step.

Additionally we could offload some of the work to the other boards. Instead of having each of the measurement boards send their raw analog values, the boards could instead convert those values to a more meaningful 0-100% scale, this would remove the work from the main board and ensure we are only sending understandable values. Another benefit of this would be less work for the main board, during our testing the main hub board got concerningly hot, and this may have been in part due to the large amount of code running on it compared to the other boards.

Another small change we could have made to the code is allowing the alarm board to play more complex sounds. Currently the alarm board is only set up to play a single note via a square wave, but it has the capability to play more complex sounds. In a hypothetical V2 software design, we could add the ability to play small melodies or have spoken prompts to convey more information to the user.


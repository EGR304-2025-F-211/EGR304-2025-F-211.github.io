---
title: Team Block Diagram
tags:
- tag1
- tag2
---

## Overview

Team 211's device consists of four unique subsystems, each with a PIC microcontroller to fulfill its desired function as an automated irrigation system, as shown by these block diagrams. The main hub, designed by Kelton, will provide shared power from a wall-mounted power supply and communication between the boards using 8-pin connectors while also displaying information through an LCD screen with a rotary encoder for user input and screen selection. To detect any failures in the irrigation system or to alert the user that the water storage tank connected to the device is running low, Hafsa's subsystem is designed to read, translate, and send information from a pressure sensor connected to the tubing and an IR sensor mounted inside the tank to Kelton's board. Levi's board uses a photoresistor to detect whether or not the plant is getting enough sunlight, and sends that data to Kelton's board. Michael's subsystem recieves information from Kelton's board about the other sensors based on their state and activates or deactivates a solenoid valve in the tubing if the plant soil is too dry and a speaker alarm if there are failures in the system.

![EGR304_BlockDiagram](image/UpdatedTeamDiagram2.png)

**Figure 1:** Team Block Diagram and Connections. PDF version [*here*](pdf/TeamBlockDiagram.pdf)


## Individual Block Diagrams

![Individual Block Diagram - Kelton Jensen](image/IndividualBlockKJ.png)

**Figure 2:** Kelton Jensen's [Main Hub Subsystem](https://kjensen37.github.io/EGR304DataSheetKeltonJensen.github.io/01-Block-Diagram/Block-Diagram)
___
   
![Individual Block Diagram - Hafsa Kaysan](image/HafsaFlowChartV2.png)

**Figure 3:** Hafsa Kaysan's [IR Reflective Sensor and Pressure Sensor Subsystem](https://hfsksn.github.io/01-Block-Diagram/Block-Diagram/)
___

![Individual Block Diagram - Levi Addink](image/LeviNewBlockDiagram.png)

**Figure 4:** Levi Addink's [Moisture and Sunlight Sensor Subsystem](https://blobiathan.github.io/01-Block-Diagram/Block-Diagram/)
___

![Individual Block Diagram - Michael Kim](image/BlockDiagramMK8.drawio.png)

**Figure 5:** Michael Kim's [Solenoid and Speaker Subsystem](https://mjkim21-dev.github.io/01-Block-Diagram/Block-Diagram/)

___

## Connections Table
![ConnectionsTable](image/ConnectionsTable.webp)


## Message structure
In the interest of not overcomplicating our messages between boards, our team opted to use simple digital and analog signals for communication. The main hub board will be doing most of the logic, while the other boards will be gathering the data. Because of this, we felt it would be redundant and unnecessary to send signals more complicated than just simple analog and digital signals, which can be easily interpreted by the hub board.

Digital signals were used as inputs and outputs when indicating a Boolean state, such as telling the speaker to activate or deactivate. Analog signals were used only as inputs for the main hub, and were used to send variable sensor data ranging such as light level or IR sensor distance.

## Top 5 software changes
The biggest significant software changes were the following

1. The motor was removed from Michael's board
Because the motor was no longer part of Michael's board, in the software, we disregarded steps involving it. There would be no moisture level check to see if it was too high or too low, and there would be no motorized response to those values as well. This was not a very complicated issue to resolve, as it only required removing existing operations and not adding new ones.

2. The moisture sensor was removed from Levi's board
Due to the moisture sensor being dropped from Levi's board, we simply changed the hub board to no longer expect any moisture values. Again, this was a simple solution as it only required removing existing operations.

Although there are meant to be 5 software changes in this list, there were actually no additional software changes besides the prior ones mentioned.


﻿
## Architecture
The project emulate three different smart objects, that are:
1. Data Collector:&emsp;&emsp;&emsp;A central object that acts as a manager that is used to execute application logic.
2. Smart Camera:&emsp;&emsp;&emsp;It takes care of capturing and sending information useful for traffic orchestration.         
3. Smart Traffic Light:&emsp; Its operating policies are set by the central controller to favor city traffic.

<img src="/Documentation/Immagini/Architettura.PNG" style="width:600px;height:600px;">

## Interaction Flow
Each smart object is associated with an executing thread, video cameras implement the Sensor interface, while semaphores implement the actuators interface. The cameras periodically publish the number of bikes, vehicles and pedestrians in their field of view. The datacollector is subscribed to the topics of the video cameras and based on the data it receives, it can set different operating policies by publishing on its topics to which the semaphores are subscribed.
The semaphores subscribed to certain topics update their operating policy as indicated by the data collector.

<img src="/Documentation/Immagini/InteractionFlow.PNG" style="width:600px;height:600px;">

## Topic Structure

<img src="/Documentation/Immagini/StrutturaTopic.png" style="width:600px;height:600px;">

## UML Schema, Project Structure and Application Scenario
For the UML schema, the project structure and the application scenario see folder [Documentation](/Documentation), there is also a pdf presentation of the project in english language.

## Usage
In order to run this project, we have to excute the classes:
1. DataCollectorEmulator
2. TrafficLightEmulator
3. SmartCameraEmulator

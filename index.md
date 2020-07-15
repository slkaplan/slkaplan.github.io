## Projects
---


### Navigating the Gauntlet: Quantitative Engineering Analysis Final Project

<img src="images/paths.JPG?raw=true"/>

Wrote a program to autonomously pilot a simulated NEATO robot from a defined starting
position and heading to a predetermined goal, through/around given obstacles. To do this, I implemented gradient descent, treating the goal as a sink and the obstacles as sources. Switching the sources/sinks would also work with slightly modified code.<br/>

[Project Github](https://github.com/samjumjum/QEA_Final_Gauntlet)<br/>
[Project Report](/pdfs/QEA_Gauntlet-1.pdf)<br/>
[Watch it in action!](https://www.youtube.com/watch?v=0D3JNF2A-vk&feature=youtu.be)<br/>


---

### Avionics Payload: Olin Rocketry

<img src="images/rocketry_stock.JPG?raw=true"/>

We had the goal of competing in the 2020 IREC Space Port America competition, but like many other things, it was cancelled due to COVID-19. I guess we'll just have to wait until 2021! As Sensing Lead, I was involved with many different aspects of the Avionics payload of our rocket. I started out the 2019-2020 year working on long distance radio communication, transitioned to apogee detection, then worked a bit on flight computer design using KiCad. Right before we had to leave campus we managed to finish assembling a prototype flight computer, which consists of a micro-controller board (a Metro Express), a long-range radio module, an altimeter, accelerometer, and GPS module all working together to track in-flight motion. 

[See our LinkedIn](https://www.linkedin.com/company/olinrocketry/)<br/>
[Look at our latest newsletter](https://drive.google.com/file/d/1WVfbE15J9MyvSEv26JRw07lrBq_T6EKL/view?fbclid=IwAR0Tkw1cy57S5X8wxqWOVlTxM09sBk1tMX0q7jO5zzXSaoWaBoWv4vcuNTQ)<br/>

### Bridge of Doom - Quantitative Engineering Analysis "Midterm"

<img src="images/bridgeofdoomThumbnail.PNG?raw=true"/>

Simulated a NEATO robot traversing a dangerous volcanic bridge using an open loop control system. The centerline of the bridge was given by a parametric curve. Used MATLAB and its ROS toolbox.<br/>

First, I had to find the unit tangent and unit normal vectors, which represent the linear and angular velocity, respectively. There are defined as follows:<br/>

<img src="images/unit.JPG?raw=true"/>

Because we were given a condition that wheel speeds cannot exceed 2 m/s (which the actual NEATO robot wheels cannot exceed, if this was done in person as intended), I set<br/>

<img src="images/you.JPG?raw=true"/>

so that wheel speed can be adjusted by total travel time. Then, using the following formulas, is should be relatively easy to find the wheel speeds.<br/>

<img src="images/speeds.JPG?raw=true"/>

Keep in mind all computation up to this point is done symbolically, as we are still missing Beta! Beta would have been easy to find, if the simulated robot also ran on "human" time. Unfortunately, there were so synchronization issues, so Beta had to be found via trial and error, which consisted of sitting infront of my computer for several hours until one of them worked. Inside each sweep of beta was another for-loop iterating over the velocity vectors each wheel. Using this method, I found a Beta of 0.32367 to get the NEATO to cross relatively consistently.<br/>

Next, we need to reconstruct the data to compare our predicted wheel speeds to our actual wheel speeds. They did indeed differ due to friction, air resistance, and all the other love things the simulation accounts for. If you are interested in the reconstruction, please see the link to the project report below. 


[Project Github](https://github.com/slkaplan/BridgeOfDoom-QEA-Spring-2020)<br/>
[Project Report](/pdfs/BOD_writeup.pdf)<br/>
[Watch it in action!](https://www.youtube.com/watch?v=pFaZ9D6f-rY)<br/>

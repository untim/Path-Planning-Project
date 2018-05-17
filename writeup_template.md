## Writeup Template
### You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---

**Path Planning Project**

* In this project, your goal is to design a path planner that is able to create smooth, safe paths for the car to follow along a 3 lane highway with traffic. A successful path planner will be able to keep inside its lane, avoid hitting other cars, and pass slower moving traffic all by using localization, sensor fusion, and map data.
* Included in the submission should be a writeup, either in the README or a seperate file that details how the project was completed.
* A great writeup should include the rubric points as well as your description of how you addressed each point. You should include a detailed description of the code used in each step (with line-number references and code snippets where appropriate) and links to other supporting documents or external references.
* All that said, please be concise! We're not looking for you to write a book, just a brief description of how you passed each rubric point, and references to the relevant code :)


[//]: # (Image References)
[image1]: ./no_incident.png

### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Your code should compile.

Done! The code compiles!

### The car is able to drive at least 4.32 miles without incident..

Tested and done!
Yup and exceeded by far
![alt text][image1]

#### The car drives according to the speed limit.

Implemented and done


#### Max Acceleration and Jerk are not Exceeded.

Implemented and done


### Car does not have collisions.

Done! The car passed the course

### The car stays in its lane, except for the time between changing lanes.

Yup also done. Lane changes happen very smooth. Sometimes if there are many cars in all lanes they happen quite frequently however the car still sticks to one lane before changing again.

### The car is able to change lanes
Yup it is.

### There is a reflection on how to generate paths.

As a starter I looked at the Q&A in order to get a general understanding what the simulator needs and how to generate smooth paths in general. This was a great help. ( Code Lines 413 in main.cpp)
I built up on the idea from the Q&A to check if certain maneuvers are possible or not possible i.e. if too_close is true (is true when the car is 30m close) then tell the car to go slower. (Code Lines 332-339 in main.cpp)
I am doing the same for changing lanes to the left or to the right. In the case when a car is ahead I am checking the left and right side of me. If there is no car on the left and on the right (is true when there is no car 20 m ahead of behind) I am giving a preference to the left side. Otherwise I am going to the right side. If neihter a left lane change nor a right lane change is possible I am waiting for the situation to change and following the vehicle ahead. (Code Lines 299-329 and 355 to 402 in main.cpp)
In my code I also included a mechanism that the car is only allowed to change lanes every 2 seconds in order to avoid continiuous lane changes. (eg Code Line 361 in main.cpp)




---
layout: default
title: Home
---

# Welcome to EECS467!
This webpage contains information for EECS 467: Autonomous Robots course at the University of Michigan.
This course discusses software methods and implementation for robot perception, world mapping, and control, using physical robots. Topics include: sensors, sensor processing, control, motion planning, localization and mapping, forward and inverse kinematics, computer vision and artificial intelligence methods. The course contains multiple team projects, culminating in a major design experience (MDE) project.  [EECS Course Bulletin](https://bulletin.engin.umich.edu/courses/eecs/).

***Prerequisites: EECS 281 and (MATH 214 or 217 or 296 or 417 or 419 or ROB 101) and (EECS 367 or 373); (C or better, No OP/F) or instructor permission.*** 


# Course Final Project Showcase:
Please see [Final Project page](https://um-eecs467.github.io//projects/) for project videos from previous semesters.

# FA 2023 Lectures:
Lecture will be held Mon./Wed. at 9a-10:30a at 104 EWRE

Also live streamed on [ZOOM](https://umich.zoom.us/j/91407802657?pwd=NVVNUk91Y0R5MDlpQUk4S1I2SWRndz09Links).

Meeting ID: **914 0780 2657**
Passcode: **516966**

Recordings of the Lectures can be viewed [HERE](https://leccap.engin.umich.edu/leccap/site/h9nsbemo6753uaqzmz7Links). (U-M Access)

# Labs:

Labs will be at EECS 3007, Fridays 12:00PM-2:00PM

# Grading:

## Part I:  Course Introduction (5%)
- MBot Intro Assignment: 5%
 
## Part II: Mobile Robotics (Botlab) (40%)
- Motion and Odometry: 15%
- SLAM: 15%
- Planning and Exploration: 10%

(Midterm - Competition)

## Part III: Design Project (40%)
- Project Proposal: 10%
- Project Update: 5%
- Project Video: 5%
- Final Presentation/Demo/Report: 20%
 
## Quiz (10%)
- Participation Grade: 5%
(Surveys, Course Evaluation, discord discussion, etc.)


# Course Staff:
{%for position in site.data.staff%}
## {{position[0]}}:
{%for people in position[1]%}
<table class="staff">
<tr>
<td><img class="staff" src="{{people.image}}" alt={{people.name}} ></td>
<td>
    {%if people.website%}
    <h2><a href="{{people.website}}">{{people.name}}</a></h2>
    {%else%}
    <h2>{{people.name}}</h2>
    {%endif%}
    <p><a href="mailto:{{people.email}}">{{people.email}}</a></p>
    <p>{{people.location}}</p>
    <p>{{people.office_hour}}</p>
</td>
</tr>
</table>
{%endfor%}
{%endfor%}


# MBot Distribution:
For FA23 semester, MBot robot kits will be available for distribution at EECS 3007 or at the Ford Robotics building.
We have a new [MBOT website](https://mbot.robotics.umich.edu/), check it out!



# References
- Thrun, Sebastian, W. Burgard, D. Fox. [Probabilistic Robotics](http://www.probabilistic-robotics.org/)
- Lynch & Park, [Modern Robotics: Mechanics, Planning, and Control](https://hades.mech.northwestern.edu/index.php/Modern_Robotics)
- Spong, Mark W., S. Hutchinson, and M. Vidyasagar. [Robot Modeling and Control](https://www.wiley.com/en-us/Robot+Modeling+and+Control%2C+2nd+Edition-p-9781119524045)
- Murray, Richard M., Zexiang Li, and S. Shankar Sastry. [A Mathematical Introduction to Robotic Manipulation](https://www.taylorfrancis.com/books/mono/10.1201/9781315136370/mathematical-introduction-robotic-manipulation-richard-murray-zexiang-li-shankar-sastry)

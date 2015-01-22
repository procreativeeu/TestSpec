Trash Management System
=======================

## 1. Introduction

Trash Management System (TMS) will be used to determine when and by who trash needs to be moved out. 

System should have a queue of collective members that are waiting to be assigned to move out the trash at the beginning of each day
or when remaining capacity of the container is not sufficient to allow for putting into it any more elements. 

## 2. Entity list

- **Trash Container** (bin) - Element that can store particular amount of trash. Capacity (cm3) is determined upon Trash Container 
creation and cannot be changed later. 

- **Trash Item** - Element that can be stored in Trash Container. Each element has it's volume (cm3) and a rate of becoming
 stinky.
 
- **Person** - User that can put Trash Items in Trash Container and also move out Trash Container when needed.
 
- **Office** - Place that has Persons and Trash Containers attached.

## 3. Queue order

Queue of members should be initially created once new Trash Container is created (each container has it's own queue).
Initial order is random (all Persons inside Office that holds new Trash Container are taken into account). Once initial
order is generated it will be generate from scratch when Person is added or removed from office. 

Initial Queue is used only to generate dynamic, priority queues when at leas one of the following events occur:

- Person that should move out the trash is getting late for Scrum at 8:15 AM
    - In that case that person will remain in the queue despite moving out the trash after arrival. 
- Person that should move out the trash is absent
    - Next person from the Initial queue is selected and person that was absent is selected to move out the trash on the very first day after coming back to the office
    
    
## 4. Assignment details

Create a application architecture (UML, Popo, Pseudo code) without using any framework or external library.
Additional requirements:

- Event driven
- PSR compliance
- Fully OO
- Complete in under 40 minutes
Troubleshooting
################

Some of the problems that we faced during this whole project and how we rectified those.

Getting Stuck
--------------

This is a problem that we face a lot when using ROS navigation. Sometimes the robot gets stuck and gives up the goal.
This was because of Global Planner Size and also system load. increasing the size of the Global Planner, this issue was solved but it used to take lot time to plan the path for far away goal point.

Inconsistency
----------------

Robots with the ROS navigation stack sometimes exhibit inconsistent behaviors. For example when entering a door, the local costmap is generated again and again with slight difference each time, and this may affect path planning, especially when resolution is low. 
It does not remember how it entered the room from the door the last time. So it needs to start out fresh again every time it tries to enter a door. Thus, if it enters the door in a different angle than before, it may just get stuck and give up.


We couldn't solve this issue. We found that it solely depends on the computation power of the system.

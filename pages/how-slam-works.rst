How SLAM Works ?
==================

Sensor Data Alignment
-----------------------

* Computers see a robot’s position as simply a timestamp dot on a map or timeline.
* Camera images are taken as many as 50-70 times a second for depth-image measurements. LiDAR scans are taken 20 times a second 
* When a robot moves, these data points help measure how far it’s gone relative to its previous location and where it is located on a map.

Motion Estimation
-------------------

* Wheel odometry takes into account the rotation of a robot’s wheels to help measure how far it’s travelled. 
* Inertial measurement units are also used to gauge speed and acceleration as a way to track a robot’s position.
* The method of odometry measurement is not accurate as it does not account for wheel slippage.

Map Building
--------------

* Maps are sparse point clouds of features that can be used mostly for localization.
* Taking measurements based on every single pixel in its field of view, the robot can build a dense map of its surroundings.
* This is called dense scene mapping and it provides the shape, size, colour and texture of the objects in its space.
* This enables much more accurate obstacle detection, avoidance, and the ability to plan movements in advance.

Algorithms
-----------

* Various SLAM algorithms are implemented in the robot operating system (ROS) libraries, often used together with the Point Cloud Library.

.. image:: ../_static/images/slam_algo.png
  :width: 500
  :alt: SLAM Algorithm Image

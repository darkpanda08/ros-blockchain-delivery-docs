Getting Started
#################

Installing Prerequisites 
---------------------------

#. Install ROS Melodic from the ROS Official Installation guide.
#. Install MoveIt: ``sudo apt install ros-melodic-moveit`` 
#. Install Gmapping: ``sudo apt install ros-melodic-gmapping``
#. Install Navigation Package: ``sudo apt install ros-melodic-navigation``
#. Install Tf2 Package: ``sudo apt install ros-melodic-tf2-sensor-msgs``
#. Install AMCL: ``sudo apt install ros-melodic-amcl``
#. Install Map Server: ``sudo apt install ros-melodic-map-server``
#. Install pyzbar python package: ``pip install pyzbar``

.. seealso::

    For `ROS Melodic Installation <http://wiki.ros.org/melodic/Installation/Ubuntu>`_

ROS Files
---------

A brief about some of the files in our ROS package ``pkg_vaccine_delivery``:

* ``city.launch`` : This file launches the simulation environment in Gazebo.

* ``vaccine.launch`` : This file spawns the robots in the arena and also initialises all the required controllers for UR5 arm and ebot movement and also the vaccum gripper service.

* ``house.launch`` : This file spawns all the vaccine boxes with the QR code in the warehouse.

* ``navigation.launch`` : This file launches the navigation stack and also the Rviz GUI for visualization.

* ``node_vaccine_ur5.py`` : This python file starts the robot 1 movement and works based upon pending task from blockchain.

.. seealso::

    Same way other python files ``node_vaccine_ur5_2.py``, ``node_vaccine_ur5_3.py`` and ``node_vaccine_ur5_4.py`` works for the robot 2, 3 and 4 respectively.




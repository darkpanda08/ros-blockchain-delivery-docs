Types of SLAM
################

Visual SLAM (vSLAM)
**********************

Visual SLAM or vSLAM calculates the position and orientation of any robot with respect to its surroundings while mapping the environment at the same time, using only visual inputs from a camera.   

It can be implemented at a low cost with relatively inexpensive cameras. Visual SLAM can use simple cameras (wide angle, fish-eye, and spherical cameras), compound eye cameras (stereo and multi cameras), and RGB-D cameras (depth and ToF cameras).

Cameras can be used to detect landmarks as well since they provide a large volume of information. In addition, since cameras provide a large volume of information, they can be used to detect a landmarks (previously measured positions). Landmark detection can also be combined with graph-based optimization, achieving flexibility in SLAM implementation.

Monocular SLAM is when vSLAM uses a single camera as the only sensor, which makes it challenging to define depth. 

.. image:: ../_static/images/vslam.png
  :width: 500
  :alt: Visual SLAM Image

Technology related to vSLAM includes structure from motion (SfM), visual odometry, and bundle adjustment.

.. image:: ../_static/images/pcl-data.jpg
  :width: 500
  :alt: Point Cloud Data

Components of vSLAM
--------------------

* The architecture of a vSLAM system includes two main components: Front-end & Back-end
* The front-end abstracts sensor data into models for estimation, while the back-end performs inference on the abstracted data produced by the front-end.

.. image:: ../_static/images/vslam_components.png
   :width: 600
   :alt: Components of vSLAM Image

LiDAR SLAM
***********

* Light detection and ranging or LiDAR is a method that primarily uses a laser sensor (or distance sensor).
* A LiDAR-based SLAM system generates a 3D map of its environment. LiDAR measures the distance to an object by illuminating the object using an active laser “pulse”.
* LiDAR is both a fast and accurate approach and can be used in a wide range of environments and conditions. 
* The output values from laser sensors are generally 2D (x, y) or 3D (x, y, z) point cloud data.
* Generally, movement is estimated sequentially by matching the point clouds. The calculated movement (travelled distance) is used for localizing the vehicle. 

.. image:: ../_static/images/2d_slam.jpg
  :width: 500
  :alt: 2D LiDAR SLAM

.. image:: ../_static/images/3d_slam.jpg
  :width: 500
  :alt: 3D LiDAR SLAM
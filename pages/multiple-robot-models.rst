Spawn Multiple Robot models in Gazebo
######################################

The Idea
----------

The whole idea of swarms robotics was derived from living beings with swarm intelligence. They essentially think as a single being and that’s what we wanted to recreate with robots. The biological examples of Swarm Intelligence.

#. A school of fishes
#. A hive of bees
#. A flock of birds
#. An colony of Ants

Approach
----------

There were 2 ways that we could see,

#. Adding prefix to each and every link and joint and all topic names etc.
#. Using Namespace

We started by updating the URDF file to add prefix to all the links and joints and topic names.
It worked pretty well for spawning the robots.
Cons of this way:

#. Each robot needed its own xacro file, because prefix need to be passed as parameter
#. Way to much editing of urdf file
#. Not at all scalable, because MoveIt needs an srdf file and as the names of links and joints are different MoveIt will need a unique srdf file with link and joints names to work.
#. That isn’t the hard part, MoveIt creates a srdf file while making the package. So, one needs make a package for each robot to be controlled

These cons were overcome by using Namespace.
In the launch file, we used <group> tags to make groups and named them ``ebot_1`` etc. This changed all the topics under that group to have a prefix ``ebot_1`` This saved us the harsh editing of the urdf file. And also, The the link and joint were named the same but were under different groups.
Encountered an error, certain topics and services were not having prefix as namespace so, after arduous searching,
If we define in urdf file the topic name as:
``/scan`` for the namespace ``ebot_1`` then the topic will be named as ``/scan``


But if the topic name is defined as ``scan`` then the topic will be named as ``/ebot_1/scan``. So, the slash in start determines if that topic has to use namespace or not.
Another problem we ran into was, due to namespace the frames were named as ``ebot_1/ebot_base`` etc. and this was not recognized by the robot state publisher because it was publishing transforms of ``ebot_base``. So, This problem was solved by adding TF prefix to the launch file and naming it the same as the namespace. This added the namespace to all the frames of that particular group and solved the problem.

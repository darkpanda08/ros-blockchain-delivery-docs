How to Integrate
#################
    
The URL of the blockchain API neeeds to be inserted in all of the ``node_vaccine_ur5_`` python files so that the ROS can communicate with the Blockchain server and request the task to be completed.
If both the API and ROS is running inside the same network, localhost URL can be used. But if both are on different network then either the ports should be opened on the API side network or tunneling should be used. 

In our case, we used ngrok, which provides secure tunnel with public URL to expose the local API server to the Internet. This URL was then used in our python file.

.. seealso::

    For more about ngrok, refer to the official website `ngrok <https://ngrok.com/>`_

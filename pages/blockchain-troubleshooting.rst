Troubleshooting Blockchain
##########################

WSL Issues
**********
* **Port issue**. Port not available or port permission denied.

The ports are being used by windows services. First stop those services, then after using those ports with docker restart windows sevices. You can use the following code in command prompt. This command has saved me multiple times.

1. ``net stop winnat`` to stop the windows service
2. Now rerun the command that gave error.
3. ``net start winnat`` this will start the windows service again.

* Sometimes while running a command there is a **random issue** as shown below. This is due problem in WSL. The problem is similar to:

.. code-block:: 

    Stopping network
    Traceback (most recent call last):
    File "docker-compose", line 3, in <module>
    File "compose/cli/main.py", line 81, in main
    File "compose/cli/main.py", line 200, in perform_command
    File "compose/cli/command.py", line 70, in project_from_options
    File "compose/cli/command.py", line 146, in get_project
    File "compose/cli/command.py", line 206, in get_project_name
    File "posixpath.py", line 383, in abspath

To solve this just write this line ``cd; cd -``

* Sometimes **WSL won't start.** When you start WSL so will only see a blank screen even after waiting for few minutes.

This problem can be solved by following these commands after restating your computer.

1. Open run by pressing Win+R.
2. type ``services.msc`` this will open windows services.
3. Find LxssManager. Right click All Tasks then Start
4. Find LxssManagerUser\_ just below LxssManager. Right click All Tasks then Start.
5. Find LxssManager. Right click All Tasks then Restart.
6. Now WSL should work.

`View this video for detailed guide. <https://www.youtube.com/watch?v=iIRrP4t8r28>`_
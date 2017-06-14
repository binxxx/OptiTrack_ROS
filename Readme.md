1. Set up ROS package as given: https://github.com/crigroup/optitrack. (Note: Do git clone in src folder)
2. Download the scripts from the Motive_track repository.
3. Copy the Rigid_body_publishers.py script and optitrack_pipeline.launch script from the hybrid robotics lab repository to the scripts and launch folder respectively.
4. Modify permissions of scripts to executable
5. Modify your IP address in the launch file (use ifconfig)
6. catkin_make in "ros_ws" dir
7. use "roslaunch optitrack Rigid_body_publishers.py iface=" read data from the Motive track.
8. rostopic echo /optitrack/rigid_bodies


Possible Issues:


1. One possible error would be 'Too many values to unpack- Exception': This can be rectified by verifying the 'unpack' function in optirx.py and making sure that 'msgtype' is returned along with the extracted data.
or Replace 'optirx.py' from '/home/.local/lib/python2.7/' with the optirx.py downloaded from this repository'
2. If "data" is not recieved by the Rigid_body_publisher.py. Copy the optirx.py file from the hybrid robotics lab repository to "/usr/local/lib/python2.7/dist-packages/optirx.py."
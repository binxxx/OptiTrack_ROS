Set up ROS package as given: https://github.com/crigroup/optitrack. (Note: Do git clone in src folder)
Download the scripts from the Motive_track repository.
Copy the Rigid_body_publishers.py script and optitrack_pipeline.launch script from the hybrid robotics lab repository to the scripts and launch folder respectively.
Modify permissions of scripts to executable
Modify your IP address in the launch file (use ifconfig)
catkin_make in "ros_ws" dir
use "roslaunch optitrack Rigid_body_publishers.py iface=" read data from the Motive track.
rostopic echo /optitrack/rigid_bodies


Possible Issues:


One possible error would be 'Too many values to unpack- Exception': This can be rectified by verifying the 'unpack' function in optirx.py and making sure that 'msgtype' is returned along with the extracted data.
or Replace 'optirx.py' from '/home/.local/lib/python2.7/' with the optirx.py downloaded from this repository'
If "data" is not recieved by the Rigid_body_publisher.py. Copy the optirx.py file from the hybrid robotics lab repository to "/usr/local/lib/python2.7/dist-packages/optirx.py."
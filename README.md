# Robot_Laser-Scanner_Object-Detecting

Generally speaking, this project aims at the following functions as initial plan

- LaserScanner sans the object such as a printed asparagus and send the positions (relative to LaserScanner) to ROS messages pool
- Object detecting algorithms subscribe the data from ROS messages pool, figure out the objects, then publish the positions to the messages pool
- Robot calibration algorithms subscribe the object positions from the messages pool, calculate the positions (Relative to Robot) and publish them into the messages pool
- MoveIt module subscribes the calibrated possitions, sends commands to the robot controller which drives the end-effectors to the top of the obeject

Author: Mengbin (Mike) Min 
Email: prlatlab@gmail.com;robotintheworld@163.com
http://prllab.wixsite.com/prl-lab-en
Copyrights Reserved

Your comments and suggestions are highly appreciated! Thanks for your time.

Tests: 
https://youtu.be/7wkOMaIlb2Y?list=PLTK_5YZhA5tG_WGu19Jo2jqEyzdOrrMiM
https://youtu.be/4BsFXOpYxok?list=PLTK_5YZhA5tG_WGu19Jo2jqEyzdOrrMiM
https://youtu.be/IIv79k23aNI?list=PLTK_5YZhA5tG_WGu19Jo2jqEyzdOrrMiM

Hardware Setup (Make sure that they are all connected correctly)
https://youtu.be/DwD2qFIzZu8

Usage:
Operating the following steps on Linux:
- roscore  (If roscore doesnot run now, please open a new terminal, please run this command) 

- sudo chmod a+rw /dev/ttyACM0  (Open a new terminal, more details available at https://github.com/ros-gbp/urg_node-release) 
    (Note for me:  /home/laserset.txt  run . laserset)
    
- rosrun urg_node urg_node  (more details available at https://github.com/ros-gbp/urg_node-release) 
    (Note for me:  /home/urgnode.txt  run . urgnode)
    
- rosrun test2 LaserScanTester (Open a new terminal)
    (Note for me:  /home/laserposition.txt  run . laserposition)
Now you can see the pulished positions like 
[ INFO] [1506564447.027778672]: 0.483479 0.450743

    
- rosrun rviz rviz (Open a new terminal)
- Add a LaserScan on rviz by clicking Add on the bottom of the left Displays panel (more details available at https://github.com/ros-gbp/urg_node-release)
- Change the Topic (Under LaserScan) to /scan (more details available at https://github.com/ros-gbp/urg_node-release)
- Change the Fixed Frame (Under Global Options) to /laser (more details available at https://github.com/ros-gbp/urg_node-release)
Now, the dots are shown on the rviz window .

# Robot_Laser-Scanner_Object-Detecting

Generally speaking, this project aims at the following functions as initial plan

- LaserScanner sans the object such as a printed asparagus and send the positions (relative to LaserScanner) to ROS messages pool
- Object detecting algorithms subscribe the data from ROS messages pool, figure out the objects, then publish the positions to the messages pool
- Robot calibration algorithms subscribe the object positions from the messages pool, calculate the positions (Relative to Robot) and publish them into the messages pool
- MoveIt module subscribes the calibrated possitions, sends commands to the robot controller which drives the end-effectors to the top of the obeject

Author: Mengbin (Mike) Min 

Email: prlatlab@gmail.com; robotintheworld@163.com

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
    
- rosrun rviz rviz (Open a new terminal)
- Add a LaserScan on rviz by clicking Add on the bottom of the left Displays panel (more details available at https://github.com/ros-gbp/urg_node-release)
- Change the Topic (Under LaserScan) to /scan (more details available at https://github.com/ros-gbp/urg_node-release)
- Change the Fixed Frame (Under Global Options) to /laser (more details available at https://github.com/ros-gbp/urg_node-release)
Now, the dots are shown on the rviz window https://www.youtube.com/watch?v=iAATysYQh3g&t=3s&list=PLTK_5YZhA5tG_WGu19Jo2jqEyzdOrrMiM&index=2.

For Simulation:
- rosrun test2 laserscantester
- roslaunch abbaspa abbga.launch has_velocity_limits:=false
    (Note for me:  /home/abbaspasimu.txt  run  . abbaspasimu)
- rosrun abb2ros motion_planning_aspa
    (Note for me:  /home/commandexecute.txt  run  . commandexecute)
You can move the object, and you can see the results as shown by the this video
https://youtu.be/ObHPCBsrXIE (A 3D_Printed Asparagus)

For Real Robot (2 ways): 

One way of using MoveIt.
(_______)

Now, the robot arm starts moving to the target object in the rviz virtural environment. If you move the object, the arm will move to a new position relatively based on the laser scanner feedback.

Another way of using internet communication without using MoveIt module
- rosrun test2 laser_aspa_pos (Open a new terminal)
    (Note for me:  /home/laserposition.txt  run . laserposition)
Now you can see the pulished positions like

[ INFO] [1506576087.330292101]: the number of points is 375

[ INFO] [1506576087.330360426]: First point: [-2.200428 -0.756997]

[ INFO] [1506576087.430859164]: the number of points is 378

[ INFO] [1506576087.430929933]: First point: [-2.169223 -0.746262]

[ INFO] [1506576087.531532844]: the number of points is 379

[ INFO] [1506576087.531611148]: First point: [-2.180571 -0.750166]

[ INFO] [1506576087.631865229]: the number of points is 381

[ INFO] [1506576087.631932325]: First point: [-2.182462 -0.750816]
    
- Change ABB IRB120 to Auto Mode 
- Run the Program called Server from T_ROB1
- rosrun abb2ros abb_ah

First the internet communication between ROS and IRC5 controller is connected.
https://www.youtube.com/watch?v=KQ2W-rRu9kg

Then the robot arm starts moving to the target object. If you move the object (it is a 3D printed asparagus for this case), the arm will move to a new position relatively based on the laser scanner feedback. Also, you can start robotstudio on Windows and monitor the robot movement online.  
https://www.youtube.com/watch?v=7wkOMaIlb2Y

Your comments and suggestions are highly appreciated! Thanks for your time.

Mengbin (Mike) Min  30/09/2017

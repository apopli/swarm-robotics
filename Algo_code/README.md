# CODE FOR ESP-8266

This is the code that runs on ESP 8266 chip. This code handles the communication between ESP 8266 chip and the server, as well as the motion control of the robot.

The code mainly focusses on two separate areas on which the function of the bot relies:

Firstly, the establishment of connection between the bots with the help of a server. 

	* The bots send a request to the server. 

	* The server takes information about the coordinates of the bots with the help of computer vision 
	and sends the data to the bots. 

	* After receiving the data it reads it and prints them to the serial. 
	From here we extract the information of the bots position and now every bot has been loaded with 
	the position of every other bot. 

	* Next, With the help of the Android app a command is received to make a particular pattern. 
	The command signal loaded on a JSON format is received through the server.

	* After this the code uploaded on the bot processes to find which bot should go to which position 
	without the intervention of the server. This part is done independently by the ESP 8266 chip on 
	the bot, which is the central concept in swarm robotics.


Now the second part of the code is to take the bots to the assigned position.

	* It does this by applying PID Control on the PWM signal of the motors of the robot. The parameter 
	to be controlled is the angle between the axis of robot and the line connecting the centroid 
	of robot and the final position. Thus the required position is finally reached.


The code is self-explanatory and important comments have been added at appropriate positions.

## RobotSim Simulate

- The instructions for the basic operation,  please refer [RobotSim Basic operations](https://yazelin.github.io/usc2019-RobotSim/zh-tw/1RobotSimBasic.html)

---

### Select a robot

- Robotic Type : KUKA KR60-L45-3 [Robotunitypackage](https://github.com/YangPeiYuan/RobotSim_Simulate/raw/master/object/KR60_L45.unitypackage)
	- Payload : 45kg
	- Max. reach: 2230cm
	
- Gripper : RGN+300-1 [Gripper Model](https://github.com/YangPeiYuan/RobotSim_Simulate/raw/master/object/RGN300.FBX)

---

### Build working objects

1. Import KUKA KR60-L45-3、Gripper RGN+300-1
	- Import RobotSim custom package                              
		 ![Image](../image/RobotSim_Import_Model.png)
		 
	- Add a Robot                                                                              
		![Image](../image/RobotSim_Import_Robot.png)

	- Add a gripper                                                                                
		![Image](../image/RobotSim_Import_New_Asset.png)
		![Image](../image/RobotSim_Import_RNG300.png)
		![Image](../image/RobotSim_Set_gripper.png)
		- Find the gripper RNG300 on the menu of SampleScene
		- Drag the gripper RGN300 into the scene and set (Position) as  (X 0, Y 0, Z 0)

		![Image](../image/RobotSim_Set_Robot_Position.png)
		- Rotate Robot w.r.t Y-axis(in Unity) at the center of the robot base with 180 degree such that the robot flange will face the gripper exactly.

		![Image](../image/RobotSim_Set_Robot_Tool.png)
		- Drag obiect RNG300 into Tool1 and set the Flange position at (0, -0.35, 0) such that the center of the flange will match to the center of the gripper RGN300 perfectly.

2. Drawing the working envelope of the robot 
	-To move the robot to observe the reach limitations          
	
	- Build a 3D spherical object                                                                      
		![Image](../image/RobotSim_Add_Range_Sphere.png)
		
	- set the scale                                                                         
		![Image](../image/RobotSim_Range_Size.png)
		- set meter as the unit
		- For example: the max reach of the robot is 2.23m, we need to set 4.46m as its diameter. 
         
         
	- set the color                                                                   
		![Image](../image/RobotSim_Range_Color.png)
		- Choose **Materials** and drag to **Element**                                     

	- Likewise, we can build the inner limitation of the robot
		![Image](../image/RobotSim_Add_Limit_Sphere.png)


3. Build the working space
	- Drawing the wall or user's defined station boundary
	- Move the robot to analyze the potential risk of interferences    
    
		![Image](../image/RobotSim_Add_Line.png)
	
		![Image](../image/RobotSim_Set_Line.png)
		- rename **Cube** as **Line** and set its length, height and positions ...
		- duplicate the **Line**above as the second one, and adjust its parameters
		- Note: the position parameter is the center of the object
                                                                                                                  
		![Image](../image/RobotSim_Set_Limit_Environment.png)
		- the working space after drawing the boundary


4. Buid the other facilitis or objects
	- Depending on the project   
	- [Box](https://github.com/YangPeiYuan/RobotSim_Simulate/raw/master/object/box.FBX)	set Length: 42CM Width: 29CM Height: 15CM 

	 - Put the box on the desired location                                  

		![Image](../image/RobotSim_Position.png)
		 - using the **Position** parameter to choose the right place for the box, unit: meter
                                                                                                                          
		![Image](../image/RobotSim_Position_Stacking.png)
		- duplicate the box and change **Position** for more other boxes on different places. Note: the height of the box is 15cm
                                                                                                                      
		![Image](../image/RobotSim_Blue_Box_Disappear.png)
		- Uncheck the object on the upper-right will delete the object from the scene, but still remaining the setting of the object. If needed, click check to use the object again  
                                                                                                                            
		![Image](../image/RobotSim_Complete_Environment.png)
		- After robot motion path analyzing, we layout the robot working space as above

--- 
### Simulation with teaching points

1. Recording teaching points

	- Using [+Point] to add teaching point 

		![Image](../image/RobotSim_Add_Point.png)
		- move robot to the picking position
		- use [+Point] to record the picking point

		![Image](../image/RobotSim_Add_All_Point.png)
	
		-  duplicate the first picking position and change the height and record as other picking points.

	- Using game object to create 
                                                                                       
		![Image](../image/RobotSim_Create_Empty.png)
		- Create an empty GameObject
		                                                          
		![Image](../image/RobotSim_Create_Blue_Box.png)
		- Rename object as BlueBox
		- drag points P1～P1(4) to the empty object
                                                                                                                                                           
		![Image](../image/RobotSim_All_Blue_Box.png)
		- duplicate BlueBox and update  P1～ P1(4) inside for other stacks
                                                                                                   
2. Programming the teaching points

	- use [Programs] for edit
                                                                                                                   
		![Image](../image/RobotSim_New_Motion.png)
		- Choose the motion type from the command menu and add its teaching point such as HomeToGreenSafe, and repaet the procedure for other points to program robot motion in the sequence of motion order. 
		                                                                                     
		![Image](../image/RobotSim_Command_Gripper.png)
		
		-  Add Gripper command object

		![Image](../image/RobotSim_Gripper_Lock.png)
		- drag **Tool1** to **Gripper** so the creating object will use tool1 as its tool.
		- Check **Lock** as object GripperLock(True)
		- Uncheck **Lock** as object GripperLock(False)
	                                                                                                                             
		![Image](../image/RobotSim_Gripper_Lock_Box.png)
		- set GripperLock(True) under the picking point for gripping box
		- set GriperLock(False) under the placing point for releasing box

 --- 
### Completed  simulation

<iframe width="560" height="315" src="https://www.youtube.com/embed/m-8mlEnRETc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQyOTc0OTEyNCwyMTM0MDI4NDM0LDIxMz
MzMDU2MjYsLTE2MTkyMDI2MzQsMTU5MDYwMTQ4NCwxNjI2MTkw
OTksLTE4NjU5NjA5NTQsLTEyNTI3MDEwODMsOTc3MjE0MjY3LC
04ODAxMzEzNDYsLTIwMDMwNDYzMTIsLTI1ODkzODIxOSwtMTkw
NjI2MTAxOCwxODM1MzEwODE0LC0xMDMxNzgwMTU2LDE4OTI0Nz
c3NTUsLTQ0OTQ4Njk0NSwtNTU3MTAyNzA3LDI3NzI4MDYxMiw2
ODUwMTU4NThdfQ==
-->
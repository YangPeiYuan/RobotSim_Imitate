## RobotSim Simulate

- 如操作過程有問題，可參考 [RobotSim基礎](https://yazelin.github.io/usc2019-RobotSim/zh-tw/1RobotSimBasic.html)

---
### 選用設備

- 機械手臂 : KUKA KR60-L45-3
	- 限制重量 : 45kg
	- 工作範圍 : 2230cm
	
- 夾爪 : RGN+300-1

---
### RobotSim建置作業環境

1. 加入機械手臂KUKA KR60-L45-3、夾爪RGN+300-1
	- 將手臂模型匯入RobotSim                                              
		 ![Robot_Model](./image/RobotSim_Import_Model.png)
		 
	- 加入機械手臂                                                                                   
		![Robot_Model](./image/RobotSim_Import_Robot.png)

	- 加入夾爪模型                                                                                    
		![Robot_Model](./image/RobotSim_Import_New_Asset.png)
		![Robot_Model](./image/RobotSim_Import_RNG300.png)
		![Robot_Model](./image/RobotSim_Set_gripper.png)
		- 將夾爪RGN300拖移到場景上，並且把位置設為原點 (X 0, Y 0, Z 0)

		![Robot_Model](./image/RobotSim_Set_Robot_Position.png)
		- 將手臂Y轉向180度，法蘭面對準夾爪

		![Robot_Model](./image/RobotSim_Set_Robot_Tool.png)
		- 將RNG300物件拉至Tool1裡，並且將Flange、RGN300位置Y各-0.35m，這樣即能將手臂Tool改至夾爪前端中心
		- 
--- 

2. 建立手臂作業空間以及極限範圍示意模型

- PS. 移動手臂時較方便目測極限距離                                                                    

	- 建立球形3D物件                                                                            
		![Robot_Model](./image/RobotSim_Add_Range_Sphere.png)
		
	- 設定物件大小                                                                                 
		![Robot_Model](./image/RobotSim_Range_Size.png)
		- 設定範圍單位為 公尺(m)
		- 例 : 手臂作業範圍2.23m，須設定圓直徑為4.46m            
         
	- 設定物件顏色                                                                                   
		![Robot_Model](./image/RobotSim_Range_Color.png)
		- 選擇Materials材質，拖移至Element欄位

	- 使用相同方法建立手臂內圈極限範圍
		![Robot_Model](./image/RobotSim_Add_Limit_Sphere.png)

4. 建立工作空間範圍

- 手臂在空間中可工作的範圍
- PS. 可用來觀察手臂運動中有無超越                                                            
	![Robot_Model](./image/RobotSim_Add_Line.png)
	
	![Robot_Model](./image/RobotSim_Set_Line.png)
	- 將Cube改名為Line並設定線的長寬高、位置等等...
	- 第二條線只需要複製並調整位置即可
	- PS. 位置參數為物件的中心，如要調整參數須注意
	- 
	![Robot_Model](./image/RobotSim_Set_Limit_Environment.png)
	- 設定完成後場景
	- 
6. 建立棧板、空箱、清洗機等物件
7. 加入夾爪並將手臂 Tool 改至夾爪前端中心
<!--stackedit_data:
eyJoaXN0b3J5IjpbODg5NjI5MzYxLC02MTYxMzE2MzQsLTgwOT
MzMTg2MSwtMjc3MzkzMjI1LDIwOTcwNjE5NjEsODExMjk5MjQ0
LC0xMjU0NDIxNDcxLC03MDEwNTAyOTUsLTQ2MTg1NjgxMiwtNj
kxNjUwODQ0LDIwNDExNjUwODAsMjk0NTQ4NjY0LC0xMzQ2OTIw
MjE0LDI5NDU0ODY2NCwxMTg3NjY2NzMsLTU5OTk0MzA1NCwxND
c1MDAxMjIsODE0NzAyMTE0LC0xNDAxODM4MDI0LDE0MzgyNDU3
MTNdfQ==
-->
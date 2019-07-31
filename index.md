## RobotSim Imitate

- 如操作過程有問題，可參考 [RobotSim基礎](https://yazelin.github.io/usc2019-RobotSim/zh-tw/1RobotSimBasic.html)

---
### 選用設備

- 機械手臂 : KUKA KR60-L45
	- 限制重量 : 45kg
	- 工作範圍 : 2230cm
	
- 夾爪 : RGN+300-1

---
### RobotSim建置作業環境

1. 加入機械手臂 KUKA KR60-L45
	- 將手臂模型匯入RobotSim                                              
		 ![Robot_Model](./image/RobotSim_Import_Model.png)
		 
	- 加入機械手臂                                                                                   
		![Robot_Model](./image/RobotSim_Import_Robot.png)
		
2. 建立手臂作業空間以及極限範圍

- PS. 移動手臂時較方便目測極限距
	- 建立球形3D物件                                                                            
		![Robot_Model](./image/RobotSim_Add_Range_Sphere.png)
		
	- 設定物件大小                                                                                 
		![Robot_Model](./image/RobotSim_Range_Size.png)
		- 設定範圍單位為 公尺(m)
		- 例 : 手臂作業範圍 2.23m，須設定圓直徑為 4.46m            
         
	- 設定物件顏色                                                                                   
		![Robot_Model](./image/RobotSim_Range_Color.png)
		- 選擇 Materials 材質，拖移至 Element 欄位

	- 使用相同方法建立手臂內圈極限範圍
		![Robot_Model](./image/RobotSim_Add_Limit_Sphere.png)

4. 建立工作空間範圍 ( 牆面、走道 )
	- 
5. 建立棧板、空箱、清洗機等物件
6. 加入夾爪並將手臂 Tool 改至夾爪前端中心
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgxNTE5NjgzOSwtNDYxODU2ODEyLC02OT
E2NTA4NDQsMjA0MTE2NTA4MCwyOTQ1NDg2NjQsLTEzNDY5MjAy
MTQsMjk0NTQ4NjY0LDExODc2NjY3MywtNTk5OTQzMDU0LDE0Nz
UwMDEyMiw4MTQ3MDIxMTQsLTE0MDE4MzgwMjQsMTQzODI0NTcx
MywxNDc3Mzc0OTY4LC02OTczNzMwODQsLTE0NjE1MTcyMzcsMT
g3NjE4NTkwNCw1ODQ3NzI1NTMsNTg4NDk3NzQzLC0xNjc5OTQ3
MzI2XX0=
-->
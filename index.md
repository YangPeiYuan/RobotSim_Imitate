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
	- 建立手臂工作範圍      PS. 移動手臂時較方便目測極限距離
		- 建立圓形3D物件                                                                            
		![Robot_Model](./image/RobotSim_Add_Range_Sphere.png)
		- 設定物件大小
			- 設定範圍單位為 公尺(m)
			- 例 : 手臂作業範圍 2.23m，須設定圓直徑為4.46m
		![Robot_Model](./image/RobotSim_Range_Size.png)
		- 設定物件顏色
		![Robot_Model](./image/RobotSim_Range_Color.png)
		
3. 建立工作空間範圍 ( 牆面、走道 )
4. 建立棧板、空箱、清洗機等物件
5. 加入夾爪並將手臂 Tool 改至夾爪前端中心
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYxMzkzODA2LDExODc2NjY3MywtNTk5OT
QzMDU0LDE0NzUwMDEyMiw4MTQ3MDIxMTQsLTE0MDE4MzgwMjQs
MTQzODI0NTcxMywxNDc3Mzc0OTY4LC02OTczNzMwODQsLTE0Nj
E1MTcyMzcsMTg3NjE4NTkwNCw1ODQ3NzI1NTMsNTg4NDk3NzQz
LC0xNjc5OTQ3MzI2LDMwMDY3ODg1MywyODQ4ODU0MTQsLTEwOT
QzNjExNzYsLTE3NTc5MzQ5OTUsNzQ1OTk4MDU1LDExMDU5NzQ4
XX0=
-->
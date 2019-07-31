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
			- 選擇 Materials 材質，拖移至 Element 格子
				![Robot_Model](./image/RobotSim_Range_Color.png)
	- 使用相同方法建立手臂內圈極限範圍
		![Robot_Model](./image/RobotSim_Add_Limit_Sphere.png)
3. 建立工作空間範圍 ( 牆面、走道 )
4. 建立棧板、空箱、清洗機等物件
5. 加入夾爪並將手臂 Tool 改至夾爪前端中心
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjk0NTQ4NjY0LC0xMzQ2OTIwMjE0LDI5ND
U0ODY2NCwxMTg3NjY2NzMsLTU5OTk0MzA1NCwxNDc1MDAxMjIs
ODE0NzAyMTE0LC0xNDAxODM4MDI0LDE0MzgyNDU3MTMsMTQ3Nz
M3NDk2OCwtNjk3MzczMDg0LC0xNDYxNTE3MjM3LDE4NzYxODU5
MDQsNTg0NzcyNTUzLDU4ODQ5Nzc0MywtMTY3OTk0NzMyNiwzMD
A2Nzg4NTMsMjg0ODg1NDE0LC0xMDk0MzYxMTc2LC0xNzU3OTM0
OTk1XX0=
-->
## RobotSim Simulate

- 如操作過程有問題，可參考 [RobotSim基礎](https://yazelin.github.io/usc2019-RobotSim/zh-tw/1RobotSimBasic.html)

---

### 選用設備

- 機械手臂 : KUKA KR60-L45-3[手臂unitypackage](https://github.com/YangPeiYuan/RobotSim_Simulate/raw/master/object/KR60_L45.unitypackage)
	- 限制重量 : 45kg
	- 工作範圍 : 2230cm
	
- 夾爪 : RGN+300-1[夾爪模型](https://github.com/YangPeiYuan/RobotSim_Simulate/raw/master/object/RGN300.FBX)

---

### RobotSim建置作業環境

1. 加入機械手臂KUKA KR60-L45-3、夾爪RGN+300-1
	- 將手臂模型匯入RobotSim                          
                    
		 ![Image](../image/RobotSim_Import_Model.png)
		 
	- 加入機械手臂                                                                                   
		![Image](../image/RobotSim_Import_Robot.png)

	- 加入夾爪模型                                                                                    
		![Image](../image/RobotSim_Import_New_Asset.png)
		![Image](../image/RobotSim_Import_RNG300.png)
		![Image](../image/RobotSim_Set_gripper.png)
		- 左方SampleScene列表找到RNG300
		- 將夾爪RGN300拖移到場景上，並且把位置 (Position) 設為原點 (X 0, Y 0, Z 0)

		![Image](../image/RobotSim_Set_Robot_Position.png)
		- 將手臂旋轉 (Rotation) Y轉向180度，法蘭面對準夾爪

		![Image](../image/RobotSim_Set_Robot_Tool.png)
		- 將左方列表RNG300物件拉至Tool1裡，並且將Flange、RGN300位置Y各-0.35m，這樣即能將手臂Tool改至夾爪前端中心

2. 建立手臂作業空間以及極限範圍示意模型

	- 移動手臂時較方便目測極限距離                                                                    

	- 建立球形3D物件                                                                            
		![Image](../image/RobotSim_Add_Range_Sphere.png)
		
	- 設定物件大小規模 (Scale)                                                                                 
		![Image](../image/RobotSim_Range_Size.png)
		- 設定範圍單位為 公尺(m)
		- 例 : 手臂作業範圍2.23m，須設定圓直徑為4.46m                         
         
         
	- 設定物件顏色                                                                                   
		![Image](../image/RobotSim_Range_Color.png)
		- 選擇Materials材質，拖移至Element欄位                                     

	- 使用相同方法建立手臂內圈極限範圍
		![Image](../image/RobotSim_Add_Limit_Sphere.png)


3. 建立工作空間範圍

	- 手臂在空間中可工作的範圍
	- PS. 可用來觀察手臂運動中有無超越或撞機風險        
    
		![Image](../image/RobotSim_Add_Line.png)
	
		![Image](../image/RobotSim_Set_Line.png)
		- 將Cube改名為Line並設定線的長寬高、位置等等...
		- 第二條線只需要複製並調整位置即可
		- 位置參數為物件的中心，如要調整參數須注意
                                                                                                                     
		![Image](../image/RobotSim_Set_Limit_Environment.png)
		- 設定完成後場景


4. 建立其他專案所需物件

	- 適各專案模擬所需使用其他物件  
	- [箱子模型](https://github.com/YangPeiYuan/RobotSim_Simulate/raw/master/object/box.FBX)	長42CM 寬29CM 高15CM 

	 - 擺放物件方式                                       

		![Image](../image/RobotSim_Position.png)
		 - 利用位置 (Position) 參數放置物體實際位置，單位均為公尺(m)
                                                                                                                          
		![Image](../image/RobotSim_Position_Stacking.png)
		- 如需要堆疊多個箱子，只需要先設定好第一個箱子位置，其餘則使用複製並更改其位置參數Y，向上移動盒子高度15CM
                                                                                                                      
		![Image](../image/RobotSim_Blue_Box_Disappear.png)
		- 選擇物件，右上角取消勾選即能將物件取消不使用，但還是能保有物件設定，需要使用時再勾選即可
                                                                                                                            
		![Image](../image/RobotSim_Complete_Environment.png)
		- 本專案經模擬後，手臂擺放位置更改成旋轉(Rotation)Y 150，此角度下手臂的工作路徑相對較順暢

--- 
### 點位記錄及模擬實作

1. 紀錄手臂點位

	- 使用位置參數設定點位 

		![Image](../image/RobotSim_Add_Point.png)
		- 將手臂移動至物件夾取位置
		- 使用 [+Point] 功能紀錄點位

		![Image](../image/RobotSim_Add_All_Point.png)
	
		-  記錄完第一點後，其他點只需要使用複製方式，並更改其位置參數(物件box高為15cm，每層點位位置Y相差0.15m)

	- 利用空物件進行分類幫助分類不同點位
                                                                                       
		![Image](../image/RobotSim_Create_Empty.png)
		- 創立一個空的物件GameObject
		                                                                               
		![Image](../image/RobotSim_Create_Blue_Box.png)
		- 將物件名稱更改為所分類名稱BlueBox
		- 將點位P1至P1(4)拖移至空物件裡面
                                                                                             
		![Image](../image/RobotSim_All_Blue_Box.png)
		- 另外6疊只需複製現有BlueBox，選取裡面P1至P1(4)點位直接移動位置
                                                                                                   
2. 將點位連接成動作

	- 使用Program編輯流程
                                                                                                                   
		![Robot_Model](./image/RobotSim_New_Motion.png)
		- 將點位分別移至所需移動方式，執行時即可讓手臂順利移置點位
                                                                                                          
		![Robot_Model](./image/RobotSim_Command_Gripper.png)
		-  使須夾取物件能夠被夾爪所夾取

		![Robot_Model](./image/RobotSim_Gripper_Lock.png)
		- 將手臂Tool拖移至Gripper
		- 下方Lock勾選為夾取物件(True)、反之取消勾選為放下物件(False)
	                                                                                                                             
		![Robot_Model](./image/RobotSim_Gripper_Lock_Box.png)
		- 將GripperLock(True)移動至預夾取物件點位下方即可夾取
		- 將GriperLock(False)移動至預放置物件點位下方即可放置

 --- 

### 完整模擬

<iframe width="560" height="315" src="https://www.youtube.com/embed/m-8mlEnRETc" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<!--stackedit_data:
eyJoaXN0b3J5IjpbODYyODQ5MjEyLDEzNzgzMzEwNjNdfQ==
-->
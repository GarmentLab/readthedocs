# RealWorld Benchmark


## Objects

|Number|Object Name |Simulation<br>Method  |Purchasing<br>Link|
| :----- | :------------|:---------|:---------|
|1| Blue Hat |FEM  |https://www.amazon.com/-/zh_TW/dp/B0D5RDGMDX?th=1&psc=1 |
|2|Short Sleeve T-shirt|PBD|https://www.uniqlo.com/jp/ja/products/E464080-000/00?colorDisplayCode=71&sizeDisplayCode=120|
|3|Cotton Coat| PBD|  https://jp.mercari.com/item/m42892132664|
|4|Long Sleeve T-shirt|PBD| https://wardrobeicons.com/product/uniqlo-white-heattech-scoop-neck-long-sleeved-thermal-top |
|5|Feather Jacket| PBD| https://www.amazon.fr/dp/B09TRPCK57?ref=cm_sw_r_apin_dp_NC71XFK61DG5NGJS69KB&ref_=cm_sw_r_apin_dp_NC71XFK61DG5NGJS69KB&social_share=cm_sw_r_apin_dp_NC71XFK61DG5NGJS69KB&language=fr-FR|
|6|Anti-bleaching Clothing|PBD| https://paypayfleamarket.yahoo.co.jp/item/z339718182 |
|7|Denim Shorts| PBD|https://www.uniqlo.com/jp/ja/products/E454469-000/00/size?sizeDisplayCode=120&measurementUnit=cm  |
|8|White Shorts|PBD|https://www.uniqlo.com.hk/zh_HK/product-detail.html?productCode=u0000000028478  |
|9|Black Pants|PBD| https://jp.mercari.com/item/m42298577821 |
|10|White Pants|PBD| https://www.uniqlo.cn/product-detail.html?productCode=u0000000051697&searchFlag=true |
|11|Blue Dress |PBD| https://www.stylehint.com/in/en/item/590234852 |
|12|Blue Denim Skirt|PBD| https://uq.goodjack.tw/hmall-products/u0000000018593 |
|13|White Camisole Vest|PBD| https://www.uniqlo.com/id/en/products/E454063-000?colorCode=COL10&sizeCode=CMC130 |
|14| White Cotton Vest|PBD| https://www.uniqlo.com/ca/en/products/E470915-000?colorCode=COL52&sizeCode=KAG150 |
|15|Blue Socks|FEM|https://www.uniqlo.com/jp/ja/products/E468785-000/00?colorDisplayCode=64&sizeDisplayCode=016 | 
|16|Yellow Rubber Gloves|FEM|https://www.walmart.com/ip/MUJI-Natural-rubber-gloves-left-and-right-handed-L-6-pack-82577129/1730217728 | 
|17|Stitch|FEM|https://www.amazon.co.jp/-/en/Disney-Stitch-Stuffed-Stitching-Birthday/dp/B0BQB1ZCRV |
|18|Winnie Bear|FEM|  https://www.amazon.sa/-/en/Disney-Plush-Classic-Value-10-5-Inch/dp/B097M8WG6Q|
|19|Straw-berry Bear|FEM| https://www.amazon.com/-/zh/dp/B0BGQM7H4S/ref=sr_1_1?dib=eyJ2IjoiMSJ9.RW6YTNXXzwpH7RkppTmqZISC8I4-OGVVt8JA3gaLTd6IfwXfuxCJyx1UFlFZYEwBNe0wKzXnd4o223R5yC4-OuuRVo_arCht5_ivDxss_TE.x9EDHa9BRtDfXaup8YbcasGvs6MMf-OeUCsxkMl1m54&dib_tag=se&keywords=lotso%2Bscented%2Bplush&qid=1722469538&sr=8-1&th=1 |
|20|Human Model<br>(Used for Scanning)|——| https://de.aliexpress.com/item/1005006515286943.html?src=google&aff_fcid=1878a49fff5e45569f28d0b64d2ec1f8-1722463187088-06512-UneMJZVf&aff_fsk=UneMJZVf&aff_platform=aaf&sk=UneMJZVf&aff_trace_key=1878a49fff5e45569f28d0b64d2ec1f8-1722463187088-06512-UneMJZVf&terminal_id=505022c486c7466e8e0af8b9b3fc564d&afSmartRedirect=n|

## Protocols
To both provide more concrete samples of the types of task definitions that can be put forward as well as specific and useful benchmarks for actually quantifying performance, we have developed some example protocols:

### Grasp Protocol
<!-- |Protocol Items|Description|
|---|------|
|**Purpose**|Assess the performance of a grasp planning algorithm in a physical robot setup,<br> evaluating whether they generalize well to different clothing items and different <br>stacking situations.|
|**Task description**|Try to grasp various types of garments in different initial states.|
|**Setup description**|**List of objects and their descriptions:**<br>Subset of the garmentlab object set,mainly consists of the following categories:<br>hats, short-sleeved T-shirts, long-sleeved T-shirts, trousers, shorts, socks, gloves,<br> jackets, dresses, skirts, vests, toys.<br> **Initial and target poses of the objects: **<br>Each object is placed at a known initial position and orientation with respect to the<br> robot. Clothes can be in many different forms, either flat or folded. For stacking, <br>randomly select some clothes and stack them together. Note that the stacking <br>situation does not take the toys into consideration.<br>**Description of the manipulation environment:**<br>There is a workbench on the horizontal ground, and all objects will be placed on the workbench. The position of the workbench is fixed relative to the robot.|
|**Robot/<br>Hardware/<br>Software/<br>Subject<br> Description**|**Targeted robots/hardware/software:**<br>- Arm/manipulator is a free choice. - Gripper choice is up to the user (number of fingers, type of actuation).- The grasp planner to be tested might be specific for a particular gripper or also generic for any type of gripper.<br>**Initial state of the robot/hardware/subject with respect to the setup:**Set up a workbench with the robot facing the workbench. The protocol considers only one piece of garment or toy in a scene (placed on the workbench), or a pile of garments placed randomly. There are no obstacles in the scene.<br>**Prior information provided to the robot:**<br>Full model of the object to be grasped is given (point cloud)<br>Gripper and arm are properly identified on the grasp planner.<br>Pose of the object with respect to the robot is given.|
|**Procedure**|**Grasp Planning:**<br>Given an object's observation point cloud, choose the best grasping position and angle. Then, the movement route is planned based on the information obtained, including the angles of each joint of the robot, the position information of the gripper, the moving speed, etc. Use the algorithm under test to plan for at least 5 grasps for each perceivable and graspable object in the layout.<br>**Grasp Execution:**<br>1. Move accordingly based on observation and grasp the object.<br>2. Lift the object 50 cm above the workbench surface and hold for 5 seconds.<br>3. Rotate the end effector 45 degrees around the approach direction to the object, in a 2 second trajectory.<br>4. Rotate the end effector -45 degrees around the approach direction to the object (back to starting position), in a 2 second trajectory. Repeat steps 3-4 two or three times.<br>5. Rotate the end effector 30 degrees around the end effector center point, in the vertical plane containing the approach direction to the object, towards the layout surface. <br>6. If operating in cluttered mode, count how many other clothes are grasped during execution of the grasp, and calculate whether the grabbing has greatly affected other unrelated clothes.<br>7. Log results. <br>8. Proceed to the next grasp or object, and back to step 1. <br>If the object slips off during any of the steps, skip to step 7. If all planned grasps for all objects have been executed, switch to the next layout and go back to planning grasps.<br>**Performance Evaluation:**<br>A grasping operation will receive a high score if:<br>1.	Select the appropriate grab point<br>2.	The grasping and subsequent movement process is stable, and no falling occurs| 
 -->

#### Purpose:
Assess the performance of a grasp planning algorithm in a physical robot setup, evaluating whether they generalize well to different clothing items and different stacking situations ( such as different poses in isolation or in clutter ).
#### Task description:
Try to grasp various types of garments in different initial states 
#### Setup description:
* List of objects and their descriptions:<br>
Subset of the garmentlab object set: mainly consists of the following categories:
hats, short-sleeved T-shirts, long-sleeved T-shirts, trousers, shorts, underwear, socks, gloves, jackets, dresses, skirts, vests, toys. 
* Initial and target poses of the objects: <br>
Each object is placed at a known initial position and orientation with respect to the robot. Clothes can be in many different forms, either flat or folded. For stacking, randomly select some clothes and stack them together. Note that the stacking situation does not take the toys into consideration.
* Description of the manipulation environment:<br>
There is a workbench on the horizontal ground, and all objects will be placed on the workbench. The position of the workbench is fixed relative to the robot.

#### Robot/Hardware/Software /Subject Description:
* Targeted robots/hardware/software:
    1. Arm/manipulator is a free choice. 
    2. Gripper choice is up to the user (number of fingers, type of actuation).
    3. The grasp planner to be tested might be specific for a particular gripper or also generic for any type of gripper.

* Initial state of the robot/hardware/subject with respect to the setup:<br>
Set up a workbench with the robot facing the workbench. The protocol considers only one piece of garment or toy in a scene (placed on the workbench), or a pile of garments placed randomly. There are no obstacles in the scene.

* Prior information provided to the robot:<br>
Full model of the object to be grasped is given (point cloud).<br>
Gripper and arm are properly identified on the grasp planner.<br>
Pose of the object with respect to the robot is given.

#### Procedure:
* Grasp planning:<br>
Given an object's observation point cloud, choose the best grasping position and angle. Then, the movement route is planned based on the information obtained, including the angles of each joint of the robot, the position information of the gripper, the moving speed, etc. Use the algorithm under test to plan for at least 5 grasps for each perceivable and graspable object in the layout.
* Grasp execution:  
    1. Move accordingly based on observation and grasp the object.
    2. Lift the object 50 cm above the workbench surface and hold for 5 seconds.
    3. Rotate the end effector 45 degrees around the approach direction to the object, in a 2 second trajectory. 
    4. Rotate the end effector -45 degrees around the approach direction to the object (back to starting position), in a 2 second trajectory. <br>
 Repeat steps 3-4 two or three times.
    5. Rotate the end effector 30 degrees around the end effector center point, in the vertical plane containing the approach direction to the object, towards the layout surface. 
    6. If operating in cluttered mode, count how many other clothes are grasped during execution of the grasp, and calculate whether the grabbing has greatly affected other unrelated clothes.
    7. Log results. 
    8. Proceed to the next grasp or object, and back to step 1. <br>
 If the object slips off during any of the steps, skip to step 7. If all planned grasps for all objects have been executed, switch to the next layout and go back to planning grasps.

* Performance evaluation:<br>
A grasping operation will receive a high score if:
    1. Select the appropriate grab point
    2. The grasping and subsequent movement process is stable, and no falling occurs 

### Fold Protocol
#### Purpose:
Assess the performance of a grasp planning algorithm in a physical robot setup
#### Task description:
Try to fold various types of garments
#### Setup description:
* List of objects and their descriptions:<br>
Use large garments from garmentlab: dresses, long-sleeved T-shirts, etc. These large pieces of clothing are simulated using PBD method.
* Initial and target poses of the objects: <br>
Garment are laid on a horizontal surface (a workbench), flattend. The target is to make this piece of cloth well-folded.
* Description of the manipulation environment:<br>
The position of the workbench is fixed relative to the robot.

#### Robot/Hardware/Software /Subject Description:
* Targeted robots/hardware/software:
    * Arm/manipulator is a free choice. 
    * Gripper choice is up to the user (number of fingers, type of actuation).
    * There can be one or two robots.

* Initial state of the robot/hardware/subject with respect to the setup:<br>
Set up a workbench with the robot facing the workbench. The protocol considers only one piece of garment in a scene (placed on the workbench). There are no obstacles in the scene.

* Prior information provided to the robot:<br>
    * Full model of the object to be folded is given
    * Gripper and arm are properly identified on the motion planner.
    * Object tracking through computer vision (Depth camera and RGB camera, capturing point cloud data).

#### Procedure:
* Fold execution:
    1. Given an object's observation point cloud, choose the best grasping position and the best placing position.
    2. Execute the planned motion.<br>
    Repeat steps 1-2 several times. (You can set a limit on the number of repetitions.)
    3. Log results.<br>
    If the object slips off during any of the steps, skip to step 3.
* Performance Evaluation:<br>
In our protocol, a folding succeeds when the Intersection-over-Union (IOU) between the target and the folded garments exceeds a bar.


### Bimanual Manipulation Protocol
#### Purpose:
The purpose is to assess the motion planning and/or learning performance of a multi-arm system.
#### Task Description:
This protocol mainly focuses on the task of gaments flinging.

#### Setup Description:
* List of objects and their descriptions:<br>
Use large garments from garmentlab: dresses, long-sleeved T-shirts, etc. These large pieces of clothing are simulated using PBD method.
* Initial and target poses of the objects and tools:<br>
Two robotic arms with grippers as end effector. Garment are laid on a horizontal surface in any shape.
* Description of the manipulation environment:<br>
A workbench is needed in the environment.<br>
(If conditions permit, you can place a bed or use the room as an experimental environment so that the clothes can eventually be placed on the bed, which is more practical.)

#### Robot/Hardware/Software/Subject Description:
* Targeted robots/hardware/software:
    * Two robotic arms, with at least 4 DoFs. Gripper choice is up to the user.
    * Force/Torque sensing not required, but likely useful.
    * Object tracking through computer vision (Depth camera and RGB camera, capturing point cloud data).
* Initial state of the robot/hardware/subject with respect to the setup:<br>
At the beginning, the two robots are in the same direction, and the workbench is in a position where both robots can easily touch any point on the table (it is recommended to consider symmetry and place it on the central axis of the robot connection). Place the clothes on the workbench.
* Prior information provided to the robot:
    * Full model of the object to be flung is given 
    * Gripper and arm are properly identified on the motion planner.
    * Pose of the object with respect to the robot is given.

#### Procedure:
* Fling execution:
    1. Select the point to grasp according to the observation, and move to reach that point.
    2. Grasp and lift the object and lift the object in front of the two robots, about 1m above the ground and hold for 5 seconds.
    3. Observe the state of the clothes at this time and record: whether they are fully stretched out or some places are still piled up, whether the appropriate grab points are selected, etc.
    4. Then quickly extend the robotic arm forward and downward, and it takes about 2 seconds to complete the fling action.
    5. Open the gripper and let the garment fall onto the plane.
    6. Observe the status of the clothes and log results.<br>
    If the object slips off during any of the steps, skip to step 6. 

* Performance evaluation:
A fling operation will receive a high score if:
    1. Select the appropriate grasp point
    2. The garments are very flat when flinging, and no falling occurs 
    3. The clothes finally lay flat on the horizontal surface without wrinkles





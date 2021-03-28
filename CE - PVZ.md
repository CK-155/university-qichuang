# 利用Cheat Engine寻找植物大战僵尸基址~~并制作修改阳光数外挂~~  
* 前置：PlantsVsZombies、Cheat Engine  
  
* 打开植物大战僵尸（以下简称PVZ），进入关卡，保持后台运行，打开Cheat Engine（以下简称CE），点击左上角小电脑图标，选择要打开的进程，选择PVZ，open  
![P1](https://github.com/CK-155/university-qichuang/blob/Photo/1.png)  
![P2](https://github.com/CK-155/university-qichuang/blob/Photo/2.png)  
* 在Value处填写现有阳光数，first scan  
![P3](https://github.com/CK-155/university-qichuang/blob/Photo/3.png)  
* 在游戏中种植物以改变阳光数，在Value中输入新的阳光数，next scan  
![P4](https://github.com/CK-155/university-qichuang/blob/Photo/4.png)  
* 双击左侧地址（如有多项可依次尝试），双击下方栏内Value值便可修改阳光数值。  
![P5](https://github.com/CK-155/university-qichuang/blob/Photo/5.png)  
* 但这个地址只是临时的，每次游戏重新启动时都会变动，所以我们要找到基址和阳光数对应的偏移量。  
* 右击该地址栏后选择Find out what accesses this address  
![P6](https://github.com/CK-155/university-qichuang/blob/Photo/6.png)  
* （如果点开后是空白，将PVZ放前台再回来就有了）  
* 会发现该地址是由[“edx”+5560]得到的，在下表我们得到“edx”的值。记录“edx”的值和偏移量“5560”。  
![P7](https://github.com/CK-155/university-qichuang/blob/Photo/7.png)  
* 将“edx”的值复制后在Value搜索（因为地址为16进制数，勾选“Hex”选项）。  
![P8](https://github.com/CK-155/university-qichuang/blob/Photo/8.png)  
* 将左侧搜索结果依次双击导入下栏，右击Find out what accesses this address后观察，出现如下图结果。  
![P9](https://github.com/CK-155/university-qichuang/blob/Photo/9.png)  
* 记录“edi”的值和偏移量“768”，并再次从Value处搜索“edi”的值。  
![P10](https://github.com/CK-155/university-qichuang/blob/Photo/10.png)  
* 如上图，本次结果较多，我们大致浏览后发现程序名开头的地址，（CE会对其标绿色字体）双击导入下栏后记录，便是基址。  
![P11](https://github.com/CK-155/university-qichuang/blob/Photo/11.png)  
* 至此我们主要过程结束。  
   
* 点击Add Address Manually，勾选pointer创建一个指针。  
![P12](https://github.com/CK-155/university-qichuang/blob/Photo/12.png)  
* 点击Add Offset，添加一个偏移量。  
* 填入基址和两个偏移量。  
![P13](https://github.com/CK-155/university-qichuang/blob/Photo/13.png)  
* 使用指针便可修改阳光数。  
  
* * *
2021.3.27 - A404  

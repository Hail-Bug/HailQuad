四旋翼无人机飞控V1.0



11/6/19   修改姿态控制和电机分配
起飞时开环，一定高度后闭环，两种模式.
1.增稳模式：遥控器给的值为给定的角度，给到内环控制，此时无外环位置环。
2.定点模式：遥控器给的值为速度，积分得到位置给到外环位置环，以此控制

遇到问题SBUS接收不到，无法进入空闲中断
U3 GPS空闲检测正常

11/8/19
选择复用时需要查芯片表

11/13/19
SBUS问题解决，引脚插错，PA11
1.遥控器输出各通道各是什么   三种模式，纯自动，position，stablise   控制通道输出为姿态角或者速度
2.手动模式下为什么两个控制器  直升机的手动模式分为纯手动和手动增稳
3.如何测试电机控制	连接电调

11/14/19
throttle channel 3
Yaw      channel 1
Pitch    channel 2
Roll     channel 4


11/27/19
发现问题 
1、罗盘需要矫正，融合后的偏航角有问题，可能是因为罗盘结算出来的角有偏差导致。
2、未装亚克力板的开发板上的MPU的陀螺仪可能有问题，偏移角速度跳动厉害。


完成了 遥控器输入的手动模式，姿态控制中偏航角为角速度P控制器。高度手动控制直接写在了PowerControl里。
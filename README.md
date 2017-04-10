# Myo-Collection
myo 臂环中肌电数据、惯性数据的采集程序，支持两个手环的数据采集和数据自动保存。基于[myo-python](https://github.com/NiklasRosenstein/myo-python)SDK

## 单个手环数据采集
__getOneMyoData.py__

采集单手的数据自动保存至Emg、Acceleration、Gyroscope中，按实验顺序标号，特点是采集频率可以达到最大，分辨率高，用于手势识别采集实验。


## 多个手环采集
__multiMyo.py__

采集两个手环的数据，用于手语采集实验。自动保存采集的数据，可通过键盘来控制采集起点和结束，以及用键盘对样本做标签。
采用多线程中键盘监听的方式，读取按键指令，定义的指令如下：
- “Enter” -> 开始该手势的采集
- “Esc” -> 结束当前手势的采集
- "T" -> 单位手势标记，每按一次标记一次
数据存储结构：

EMG:

List[ EMG of Myo 1 , EMG of Myo 2 , tag ]

    [   1 x 8      ,    1 x 8     ,  1  ]
    
List[ EMG of Myo 1 , EMG of Myo 2 , tag ]



Acc & Gyr:

List[ data of Myo1 ,data of Myo2  ]

[   1 x 3      ,    1 x 3     ]

List[ data of Myo 1 , data of Myo 2 ]

## 依赖
- [myo-python](https://github.com/NiklasRosenstein/myo-python)
- [PyWin32](http://www.lfd.uci.edu/~gohlke/pythonlibs/)
- [PyHook](http://www.lfd.uci.edu/~gohlke/pythonlibs/)
 



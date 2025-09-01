## **项目概述**

本项目是基于 Seeed Studio Wio Terminal 开发板对史上第一款电子游戏《Tennis for Two》的现代复刻版。原版游戏由 William Higinbotham 于1958年创造，本版本在保留经典核心玩法的基础上，引入了现代游戏元素，如关卡系统和智能AI对手。

游戏采用物理基础的球体运动机制，支持球拍碰撞检测，并具有随关卡提升的自适应AI难度系统。通过简洁的用户界面显示分数和游戏状态信息，这款实现将游戏历史的一件珍品带到了现代硬件平台上。

## **功能特点**

**经典玩法:** 在原版 Tennis for Two 的游戏机制基础上实现创新性玩法

**渐进难度:** 5个关卡，球速和AI反应速度逐级提升

**直观控制:** 简单双键控制方案（A键右移，C键左移）

**简洁界面:** 实时分数显示、关卡指示器和游戏状态画面

**自适应AI:** 能够追踪和预测球路的计算机对手

## **硬件要求**

| **组件** | **数量** | **备注** |
| --- | --- | --- |
| Wio Terminal | 1   | 包含显示屏、按键等所有必要组件 |

## **引脚使用**

**A键:** 向右移动

**C键:** 向左移动

## **软件要求**

**Arduino IDE 2.3.6** 或更高版本

**开发板支持包:** Seeed Studio SAMD Boards

**依赖库:**

TFT_eSPI (用于显示输出)

Seeed_Arduino_Button (用于按键输入处理)

## **安装与设置**

1.从[官方网站](https://www.arduino.cc/en/software"%20\t%20"https://chat.deepseek.com/a/chat/s/_blank)安装Arduino IDE  
https://www.arduino.cc/en/software/#ide

2.添加Wio Terminal开发板支持：

打开您的 Arduino IDE，点击 File > Preferences  
并将以下网址复制到Additional Boards Manager URLs:  
添加: https://files.seeedstudio.com/arduino/package_seeeduino_boards_index.json
![图片alt](https://files.seeedstudio.com/wiki/Wio-Terminal/img/Boardurl.png)

从开发板管理器安装"Seeed Studio SAMD Boards"
点击 Tools > Board > Board Manager 并在开发板管理器中搜索 Wio Terminal。
![图片alt](https://files.seeedstudio.com/wiki/Wio-Terminal/img/addBoard.png)

选择您的开发板和端口  
您需要在 Tools > Board 菜单中选择与您的 Arduino 对应的条目。 选择 Wio Terminal。  

在Arduino IDE中打开 Wio_Tennis_for_Two.ino

选择开发板: "Seeed Studio Wio Terminal"
![图片alt](https://files.seeedstudio.com/wiki/Wio-Terminal/img/selectBoard.png)

将代码上传到您的Wio Terminal

## **游戏说明**

**开始游戏**

启动Wio Terminal

在开始画面按任意键开始游戏

**控制方式**

A键: 向右移动球拍

C键: 向左移动球拍

**游戏玩法**

防止球到达底部边界

用球拍击球将其打回

当球通过AI的上边界时得分

获得7分后进入下一关卡

如果AI获得7分，游戏结束

完成所有5个关卡以赢得游戏

**项目结构**

text

Wio_Tennis_for_Two/

├── Wio_Tennis_for_Two.ino # 主程序 (setup(), loop())

├── game_logic.h # 游戏状态、对象定义、碰撞检测

├── game_logic.cpp # AI逻辑和游戏机制实现

├── graphics.h # 屏幕绘制函数声明

├── graphics.cpp # 界面渲染实现

├── input.h # 按键输入处理声明

└── input.cpp # 输入处理实现

**关键函数**

checkCollision(): 检测球与边界和球拍的碰撞

updateAI(): 根据球位置控制计算机对手移动

drawGame(): 将所有游戏元素渲染到显示屏

checkInput(): 处理玩家按键操作

## **开发阶段**

**阶段一: 最小可行产品**

在屏幕上渲染静态的球和球拍

实现基础球体运动和边界碰撞

添加通过按键的球拍控制

实现球拍碰撞物理效果

创建基础计分系统

**阶段二: 功能完善**

开发AI对手逻辑

添加渐进关卡系统和难度缩放

实现游戏状态（开始、游戏中、游戏结束、胜利）

**阶段三: 优化改进**

代码精炼和注释

性能优化

技术细节

物理实现

游戏使用真实的物理效果实现球的运动和碰撞：

球的速度受击球点在球拍上的位置影响

碰撞角度基于撞击点计算

速度随着关卡提升而增加

**AI系统**

计算机对手采用基于状态的方法：

预测球的轨迹以预判未来位置

根据当前关卡调整移动速度

包含随关卡提升而减少的误差范围

**显示渲染**

320x240像素TFT显示屏

使用差异渲染实现高效的屏幕更新

带有分数和关卡指示器的简洁UI

## **未来增强**

未来版本的潜在改进：

使用内置蜂鸣器添加音效

使用内置振动电机提供触觉反馈

带有持久存储的高分记录功能

多游戏模式选择

可调节难度设置

## **关于原版游戏**

《Tennis for Two》由物理学家William Higinbotham于1958年在布鲁克海文国家实验室创建。它旨在在年度开放日期间娱乐访客，被认为是史上最早的电玩之一，甚至早于《Spacewar!》和Magnavox Odyssey。  

## **许可证**

本项目是开源项目，采用MIT许可证。  

## **致谢**

Seeed Studio提供Wio Terminal硬件

William Higinbotham创建了原版游戏

Arduino社区提供广泛的库和支持

## **贡献**

欢迎提交贡献、问题和功能请求。如果您想参与贡献，请查看问题页面。  

## **开发者**

邓宇淇（Yuki）

本项目用于教育和娱乐目的。Tennis for Two是电子游戏历史上的历史文物。

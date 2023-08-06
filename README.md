<!--
 * @Author: Chengsen Dong 1034029664@qq.com
 * @Date: 2023-08-02 23:53:02
 * @LastEditors: Chengsen Dong 1034029664@qq.com
 * @LastEditTime: 2023-08-06 18:50:20
 * @FilePath: /arm-NES-linux/README.md
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
# arm-NES-linux emulate for InfoNES open source
## Planform
	Raspberry Pi or Arm linux or ubuntu
	Direct draw /dev/fb0 Framebuffer

## Build
	cd arm-NES-linux-/linux/
	make

## Build joypad linux kernel module
	cd arm-NES-linux-/joypad/
	make


## USE
	insmod joypad.ko
	cd arm-NES-linux-/linux/
	./InfoNES SuperMario.nes

## Change Log
	2020-07-05 Add Qt project

## Preview
![avatar](https://github.com/nejidev/arm-NES-linux/blob/master/Qt/qt_nes.jpg?raw=true )

## 说明
	为什么会有这么样一个项目，起初发现有人在 STM32F103上实现了，于是找到源码开始研究，最早可以在 ARM 裸板上运行，
	但是 ALSA 的声音一直有问题，后来修复。
	最近又在学习 QT 于是，用 QT 重新适配一版。
	Qt 对中文支持不好，所以请不要选择带有中文路径的 nes 文件。


# xddcore add 2023/08/03:

1. 安装`alsa-utils`音频组件
```
apt install alsa-utils
apt install libasound2-dev
apt install zlib1g-dev
```

2. 编译
```
cd arm-NES-linux/linux
make
```

3. 下载游戏
```
wget https://github.com/xddcore/arm-NES-linux/releases/download/NES_Test_Game/Super_Mario_Bros_3.nes
```

4. 运行测试游戏🎮(超级马里奥)
```
#注意切换为自己的超级马里奥游戏路径
./arm-NES-linux/linux/InfoNES ./Super_Mario_Bros_3.nes
```

5. 键位映射关系表

 |  Joy   |USB键盘  |
|  ----  |---- |
| UP | W |
| DOWN  | S |
| LEFT | A |
| RIGHT  | D |
| SELECT | 空格 |
| START  | 回车 |
| A | K |
| B  | L |
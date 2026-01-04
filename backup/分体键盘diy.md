# 前期调研

### 套件选择：

  平面：lily58,lily58pro,sofle keyboard（sofle相当于加了旋钮的lily58),[Ergodone](https://post.smzdm.com/p/487452/)(大号分体）, crone(没有数字区不适合打中文）,[Redox](https://botiostudio.com/redox-keyboard-split-ergo/)(大号分体）,Helix(纯平面）

  曲面：dactyl manuform

目标：便携，易用，能用上现有的材料.容易制作，开源，有丰富的案例,轴座为热插拔

结论：[sofle v2](https://josefadamcik.github.io/SofleKeyboard/build_guide.html)(v1和v2的区别是v1支持矮轴）

主要目标：复刻sofle v2

次要目标：把旋钮改成摇杆,加入缓震材料

主要工具：吸锡器，焊笔，放大镜

前期补充资料：

[Pro Micro & Fio V3 Hookup Guide - learn.sparkfun.com](https://learn.sparkfun.com/tutorials/pro-micro--fio-v3-hookup-guide)

[Inverted silkscreen? · Issue #3 · josefadamcik/SofleKeyboard · GitHub](https://github.com/josefadamcik/SofleKeyboard/issues/3#issuecomment-683192038)

## 物料清单

[材料清单](https://www.wolai.com/wocobD2oxbodEEgXWohuAo)

- [x] 凯华轴座58个
- [x] pcb打板
- [x] 定位板和底板
- [x] **1N4148W** SOD123 package 58
- [x] ssd1306 128*32 oled 2
- [x] 音频端子 2
- [x] 音频线
- [x] 两脚轻触开关 2
- [x] m2 6mm 铜柱 14个
- [x] m2螺丝 28
- [x] 防滑贴
- [x] EC11编码器 2（最好是ec11e,不要是ec11k)
- [x] 旋钮盖
- [x] pro micro ATmega32U4
- [x] 凯华轴座58个
- [x] pcb打板5
- [x] 定位板和底板2
- [x] **1N4148W** SOD123 package 58
- [x] ssd1306 128*32 oled 2
- [x] 音频端子 2
- [x] 音频线 1
- [x] 两脚轻触开关 2
- [x] m2 6mm 铜柱 14个
- [x] m2螺丝 28
- [x] 防滑贴 1
- [x] EC11编码器 2（最好是ec11e,不要是ec11k)
- [x] 旋钮盖 2
- [x] pro micro ATmega32U4 2
- [x] 收货确认



## 固件和编程

![](https://secure2.wostatic.cn/static/6FEDHJ3mYGW4QDc96MMdon/image.png?auth_key=1767516045-kBjiNdh8QZE8dg9A3PpCHz-0-7b712f1ba8de1d624c0da4f1bf0f91a1)

[qmk教程](https://www.wolai.com/vAcvf8xEfaBSCkAAbtppwz)

1. 确保qmk的环境设置好
2. 不要连接trrs音频线
3. 将一半的键盘连接到电脑上面,flash固件,使用reset按钮
4. 另外一半的键盘也要如此
5. 断开usb连接，将两个键盘用trrs连接
6. 用usb线连接左边的键盘
7. **Enjoy!!!**

## 时间表

**2021.11.23-24**

周二或周三物料和工具到齐

**2021.11.24-12.1**

焊接预计时间为一到两天，刷入固件

**ddl暂定12月1日**

### 日志

2021/11/26

问题：只有单一的板子工作，另外一块板子电源亮，指示灯亮，但是无法工作，oled屏幕显示乱码

[Split Keyboard (qmk.fm)](https://docs.qmk.fm/#/feature_split_keyboard?id=required-hardware)

![](https://secure2.wostatic.cn/static/bwYTwykGUCscfvqLQ2Vb4j/image.png?auth_key=1767516045-tyjAbaKDEMhQ7y3KEf4UJp-0-ac6813d9c76d4035e2ee847343444f1a)

![](https://secure2.wostatic.cn/static/szAqURkx5pQRen7EHb3wi9/image.png?auth_key=1767516045-kEqKuUDGBHpDKqh5859kkm-0-8b4150d9cb37adc74652845cf613e77b)

![](https://secure2.wostatic.cn/static/szAqURkx5pQRen7EHb3wi9/image.png?auth_key=1767516045-bVxsgk73tQrxDjc5Fw6f5m-0-8ced5b803c6282cf1b49aeaf3179a251)

`avrdude-split-left`/`:avrdude-split-right`

![](https://secure2.wostatic.cn/static/gt7p39ZenLsEiB6bch6ZDg/image.png?auth_key=1767516045-fN3zdtvwzPkf3ah3vvK1x1-0-1787d3ffbe9bdfd3a3d5ce66c7ee491f)

2021.11.28

严重大问题，两个板子无法通信，已知接线没有问题，单独拿杜邦线连接的时候也没用😩

迷之解决办法:把一块板子的vcc和另外一块板子的gnd互连。估计这样电路重置了，可能是板子本身有问题。

买加长的母插让oled有合适的位置

目前via还是无法识别设备



2021/11/29

via无法识别，换电脑解决了，虚拟机也可以用。考虑要不要重装电脑。

[via教程](https://www.wolai.com/tk1tqCzB9TBZzVqbeDUtft)



## 注意

1. 轴座的位置不要放反，不然轴体无法插入
2. pro micro和oled的高度要不一样，要买不同高度的排插和母座
3. 焊板子的时候不要焊弯针脚
4. 螺丝要买机钉螺丝，不要买自攻





## 未来展望：

加入轨迹球或者摇杆

[GitHub - foureight84/sofle-keyboard-pimoroni: Pimoroni Trackball integration with Sofle Keyboard](https://github.com/foureight84/sofle-keyboard-pimoroni)

 I2C pins are still available on the V2 revision as per this [reddit post](https://www.reddit.com/r/ErgoMechKeyboards/comments/o3zwgn/sofle_v21_rgb_pcb_with_trackball/) by [tenstaana](https://www.reddit.com/user/tenstaana/)

[Sofle v2.1 RGB pcb with trackball : ErgoMechKeyboards (reddit.com)](https://www.reddit.com/r/ErgoMechKeyboards/comments/o3zwgn/sofle_v21_rgb_pcb_with_trackball/)

[轨迹球单手键盘 QMK RGB 热拔插_键盘_什么值得买 (smzdm.com)](https://post.smzdm.com/p/akx8kx78/)

[https://post.smzdm.com/p/aqxqd5xp/](https://post.smzdm.com/p/aqxqd5xp/)

分析：国外方案是采用pimoroni的trackball breakout,暂时找不到购买方案，而且五个针脚刚刚合适

[Trackball Breakout – Pimoroni](https://shop.pimoroni.com/products/trackball-breakout)

![](https://secure2.wostatic.cn/static/kfT3t2qBZkpP4Qx5pFmg9c/8x2uxj82gd671.jpg?auth_key=1767516045-iExhByGVfWYjNAF63GUNur-0-dcdbf7061f450c19b3877fa26fac7d9e)

![](https://secure2.wostatic.cn/static/vRSM69qcmLddHMw54aBWeh/image.png?auth_key=1767516045-m7GmjFexitnRSrsAddWy1T-0-8effefc34c0b3fee816887aa9493b3ea)







ps2摇杆

[PS2游戏摇杆原理及控制实现_按键 (sohu.com)](https://www.sohu.com/a/417990890_100281310)

[Arduino简单实例之四_PS2游戏摇杆_谢彦的技术博客-CSDN博客_arduino ps2](https://blog.csdn.net/xieyan0811/article/details/56011832)

![](https://secure2.wostatic.cn/static/c3vZUrmMZyfyEiRvF15guU/image.png?auth_key=1767516045-brtwLBVFKmStqo9TnwaUJX-0-3b06aa037e6d38dc412b9d9afb8f7e02)



罗技逻辑球，简单易改造，只需要塞入合适的位置，不需要管固件

[轨迹球板+PS2母转USB公转接头板 PS2键盘鼠标转换 一套价 diy-淘宝网 (taobao.com)](https://item.taobao.com/item.htm?spm=a230r.1.14.19.355d6860DNoMpO&id=621149796065&ns=1&abbucket=12#detail)

[https://post.m.smzdm.com/p/avw7z3qp/](https://post.m.smzdm.com/p/avw7z3qp/)?



![](https://secure2.wostatic.cn/static/tTDak7HEUApnxmEQXHEab1/image.png?auth_key=1767516045-wWYMav1Ct53ymA6UD6Nkir-0-bc0e5b18a8d9b730931136084c5e25aa)

触摸板：

[HTT5288 eKT2101 eKTF2132 CY8CTMA463-4QI 触摸板-淘宝网 (taobao.com)](https://item.taobao.com/item.htm?spm=a230r.1.14.1.76829061q5nU1X&id=586856886897&ns=1&abbucket=12#detail)

（有试错成本的）



自制键帽：３ｄ打印，树脂

[没有合适的键帽怎么办？3D打印呀！不会建模？不需要！_其他数码配件_什么值得买 (smzdm.com)](https://post.smzdm.com/p/aqn9px9k/)



trackpoint小红点



搖桿控制滑鼠

QMK配合幾款搖桿小心得

1.

最上面那款使用起來最簡單

基本上就是一種開關

往哪個方向扳那個方向的訊號就會跟common點導通

所以用QMK的話只要當一般掃描按鍵時的接法和設定方法設定KC_MS_*那些按鍵就可以直接使用

要說缺點就是要用的pin腳有點多

2.

中間那款搖桿原理是用電位器(可變電阻)方式分壓

使用上就稍微需要用到Analog輸入相關的東東

我也是抄人家的原始碼才會使用

(qmk_firmware/keyboards/40percentclub/nano/keymaps/drashna)

優缺點除了控制上比較複雜和多用一些程式碼控制外

再來其實就是數位和類比的差別

需要pin比較少

但那個pin腳其實就是用ADC換來的

還好我那塊teensy++ 2.0剛好Analog輸入Pin腳空著所以才有辦法加上去

3.

最下面這款

這個軌跡球其實還沒試

之前有看到大大有用過

但是是用Arduino IDE開發的

直接用qmk compile的話

還不確定一些function如pulseIn()有沒有辦法移植過來

![](https://secure2.wostatic.cn/static/wqJTgdwrBMrU3Gn7rgJZAQ/image.png?auth_key=1767516045-wXWsTT1DszScSfcu8phgD4-0-22705d15a235739e94a0e0a056acddf5)

### 新购入配件

- [ ] 触控板
- [ ] 轨迹球
- [ ] nfc标签贴



## 经验

pcb设计的时候可以采用双面或者可以部分掰断的设计，来减少打样的费用

mitosis设计中，甚至pcb本身可以是定位板



## 无线分体键盘

mitosis

[GitHub - YCF/mitosis-mod: Only for my personal version:[mitosis-hardware-mod](https://github.com/YCF/mitosis-hardware-mod)]([https://github.com/YCF/mitosis-mod](https://github.com/YCF/mitosis-mod))



redox-wireless

[GitHub - mattdibi/redox-w-firmware: Firmware for nordic MCUs used in the Redox wireless keyboard](https://github.com/mattdibi/redox-w-firmware)

[https://github.com/mattdibi/redox-keyboard/tree/master/redox-w](https://github.com/mattdibi/redox-keyboard/tree/master/redox-w)

interphase

[GitHub - Durburz/interphase: a mitosis clone with more keys!!1eleven](https://github.com/Durburz/interphase)



蓝牙固件

[GitHub - Durburz/interphase-firmware: Firmware for interphase (a mitosis clone)](https://github.com/Durburz/interphase-firmware)

bluemicro

[GitHub - jpconstantineau/BlueMicro_BLE: Keyboard Firmware for the Nordic nRF52 Series of Bluetooth SoC based on the Adafruit NRF52 Feather](https://github.com/jpconstantineau/BlueMicro_BLE)

zmk

qmk nrf52分支



主控

[GitHub - joric/nrfmicro: Pro Micro-compatible Bluetooth 5.2 board with Li-Po charger and USB-C (nRF52840-based)](https://github.com/joric/nrfmicro)



便宜主控

nRF51822



预计采取redox-w项目



# Redox-w

[redox-keyboard/redox-w at master · mattdibi/redox-keyboard · GitHub](https://github.com/mattdibi/redox-keyboard/tree/master/redox-w)

[新手向-DIY无线分体键盘Redox_w-02-制作教程（无楠度）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV15q4y1y7Ty?from=search&seid=12739197624034511875)

material list



购买检查

收货检查

- [x] PCB*4
- [x] 底板和定位板
- [x] 凯华轴座*70
- [x] nrf51822*3
- [x] pro micro*1
- [x] 1117 SOT223 *1
- [x] white led *4
- [x] 330r 电阻 *2
- [x] 220r 电阻 *2
- [x] 1.5kr 电阻 *2
- [x] 轻触开关*1
- [x] SOD-123 1N4148/1N4148W *70
- [x] JS102011SAQN开关三脚二档位
- [x] 4p 90度排针 *2
- [x] 6p母座*2
- [x] STLinkV2
- [x] 3034纽扣电池座



- [x] PCB*4
- [x] 底板
- [x] 定位板
- [x] 凯华轴座*70
- [x] nrf51822*3
- [x] pro micro*1
- [x] 1117 SOT223 *1
- [x] white led *4
- [x] 330r 电阻 *2
- [x] 220r 电阻 *2
- [x] 1.5kr 电阻 *2
- [x] 轻触开关*1
- [x] SOD-123 1N4148/1N4148W *70
- [x] JS102011SAQN开关三脚二档位
- [x] 4p 90度排针 *2
- [x] 6p母座*2
- [x] STLinkV2
- [x] 3034纽扣电池座
- [x] 纽扣电池(CR2032)*2



接收器led电阻

![](https://secure2.wostatic.cn/static/6ktbN87GZKiGbzehmPjfnU/image.png?auth_key=1767516045-gPHvhWP9NttMGDJjrxHU6A-0-49dfabda10a9b1da24a0e6b769d089c0)

![](https://secure2.wostatic.cn/static/dh3Kjk3ruYf3FifY5MmKTb/image.png?auth_key=1767516045-eeJkRxCf8CuhK1Tchp3kEJ-0-44a3a84151cb15131e638b7ba3f403a8)



## 日志

2022/01/09已购买全部原材料

2022/01/12 发现定位板的图纸有问题需要重新修改, 考虑要不要重新做

2022/01/13定位板和底板打孔有问题， 缺少适合的工具和技术，导致一个nrf51822掉了一个焊盘

2022/01/17通过直接短接芯片的引脚发现是可以正常触发的，意味着通信和刷入是成功的,新的模块无法再次刷入，可能有点问题，等热风枪。而且没有注意左右手。用风枪的时候记得考虑一下温度。

拆机轴无法触发是因为带着锡会导致金属片产生便宜。目前解决办法是，拆开轴体安装完之后再装回去。



## 焊接

注意焊接顺序，安装官方的来

1. Solder D1, D2, D3 and D4 LEDs. See [image](https://github.com/mattdibi/redox-keyboard/tree/master/redox-w#leds-installation-detail) for orientation.
2. Solder R4, R6, R7 and R8 resistors.
3. Solder R1, R2 and R3 resistors.
4. Solder the AMS1117.
5. Solder the Arduino Pro Micro headers.
6. Solder the programming headers. I suggest you to cut the excess of the header **before** soldering the headers. You should stay as flush to the PCB surface as possible since the controller will be soldered above the headers. Use some masking tape to help you keep the header in place while soldering.
7. Solder the YJ-14015. I suggest you to glue it in place or use some masking tape to help you during soldering.
8. Upload the firmware and you're done.



1. Solder the YJ-14015.
2. Solder the right angle 0.1" header. To test the solder job try uploading the firmware as described in the dedicated section.
3. Solder the diodes taking into account the right orientation. The cathode side (denoted by the vertical line on the packaging) should face the squared hole on the PCB. See the [pictures](https://github.com/mattdibi/redox-keyboard/tree/master/redox-w#diodes-and-hot-swap-socket-detail) for reference. If you have already assembled the Redox receiver, you can now test if the PCB is working properly by connecting the STLinkV2 debugger for supplying power to the transmitter and using a pair of pliers to short the Kailh socket pins.
4. Solder the Kailh hot-swap sockets.
5. Solder the battery holders.
6. Solder the slide switch.

## 烧录

概括：promicro刷qmk,nrf用docker刷固件

![](https://secure2.wostatic.cn/static/sbKuzaCb4yfuEjVYm4rRqv/20211216 114427791.png?auth_key=1767516045-r7AUPEUNVwYFgvzGydQmun-0-0239065c69e55f0dc80628e3d15ad03e)



[Windows 10里的WSL Ubuntu 怎么使用Windows系统的 SS 代理?_清晨的光明-CSDN博客_wsl 使用windows代理](https://blog.csdn.net/kdongyi/article/details/105620754)

[wsl2 ubuntu20.04子系统使用win10代理_程序员的博客-CSDN博客](https://blog.csdn.net/q85795362/article/details/120283801?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~default-1.no_search_link&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~default-1.no_search_link&utm_relevant_index=1)

cd path/to/repository/redox-w-firmare/

$ sudo cp 49-stlinkv2.rules /etc/udev/rules.d/

$ udevadm control --reload-rules && udevadm trigger

sudo docker-compose build

sudo docker-compose up

接收器

sudo docker exec -it redox-w-firmware_toolchain_1 ./redox-w-firmware/redox-w-receiver-basic/program.sh

左侧

sudo docker exec -it redox-w-firmware_toolchain_1 ./redox-w-firmware/redox-w-keyboard-basic/program_left.sh

右侧

sudo docker exec -it redox-w-firmware_toolchain_1 ./redox-w-firmware/redox-w-keyboard-basic/program_right.sh



jvlink ob 刷固件办法

[新手向-DIY无线分体键盘Redox_w-02-制作教程（无楠度）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV15q4y1y7Ty?from=search&seid=12739197624034511875)

### 接收器

#### Arduino Pro Micro Firmware upload

$ cd path/to/qmk_firmware
$ make redox_w:default:avrdude

记得rule.mk里面加上VIA_ENABLE = yes 才能使用VIA

nrf51822

进行到这一步还无法执行

$ udevadm control --reload-rules && udevadm trigger

放弃wsl，用虚拟机已经执行成功，注意使用ubuntu desktop版本server暂时没解决ssh问题

vm启动ubuntu的速度过慢



外设相关配件

![](https://secure2.wostatic.cn/static/odo6pWUh3wpkoRoVeS8R4v/image.png?auth_key=1767516045-jevKFGeok8wRePb4H8Awcu-0-c4433b2a2e22957c21a32ab3c5965863)

## 未来展望

锂电池充电
---
layout:     post
title:      Game Error | dxgierrordevice_removed
subtitle:   dxgierrordevice_removed
date:       2018-08-22
author:     SLX 
header-img: img/post-bg-independent_thinking.png
catalog: true
tags:
    - Game
    - Windows
    - error
---
你用 windows 玩游戏的时候也遇到了突然的弹窗，说什么dirextx出了问题？
>（dxgi_error_device_removed 0x887a0007, 0x887a0006, 0x887A0002 and 0x887a0005）

那么可以尝试一下以下操作：

1. 点击 “windows” 按钮
2. 键入 “regedit” 或者 “注册表编辑器” 以查询软件
3. 右击 “以管理员身份运行”
4. 在左边的列表按以下顺序查找：
    HKEY_LOCAL_MACHINE -> SYSTEM -> CurrentControlSet -> Control
    点击 GraphicsDrivers 
5. 右击 GraphicsDrivers
    然后点击 “新建” -> DWORD(32位）值
6. 在右边窗口中输入值 TdrLevel （注意T和L必须大写，没有空格）
7. 双击进入，确认数值为0
8. 重启电脑

那么这个问题的原因是什么？
根据国外油管相关大神的说法是系统的一种自我防御机制，防止显卡在一定时间内不回应，TDR机制会去重置它。所以当一些进程使显卡果冻住，就会诱发使用的进程崩溃掉。

这里的做法其实就是关闭这种机制。
但是这样不一定能解决所有人的问题，有人会遇到设置之后导致画面果冻住，只能按开关键重启，这时候大家可能要查一下以下原因：

有人回复说显卡有质量问题或者超频的也会导致这样的问题。
希望可以解决大家的问题。
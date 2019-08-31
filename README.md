# Hackintosh_E450C 

![图像 2019-8-22，07 29](https://user-images.githubusercontent.com/9806325/64062526-0c5abd00-cc1a-11e9-8b42-2e1df296b89d.jpg)
![图像 2019-8-22，07 32](https://user-images.githubusercontent.com/9806325/64062519-ee8d5800-cc19-11e9-9d16-c6b96ae1a47d.jpg)
![图像 2019-8-22，07 35](https://user-images.githubusercontent.com/9806325/64062520-f220df00-cc19-11e9-9885-bf9263448288.jpg)
![图像 2019-8-22，07 51](https://user-images.githubusercontent.com/9806325/64062521-f5b46600-cc19-11e9-94b3-7089b40b00be.jpg)



E450C 黑苹果目前已经完成一下功能：

* IGPU Hotpatch驱动完成。

* HDAU 注入ID 27 完美进行切换，一切正常

* 亮度调整完成，FN+K降低亮度，FN+P提高亮度

* 注入Retina显示器

* LPC注入

* 更新至macOS 10.14.2 修复花屏睡眠无法唤醒问题。
未完成：

* HDMi外接屏幕

Clover 文件夹内包含


* Config.plist
    * 自行增加三码，个人使用三码已经剔除。

    * 去除ig-platform-id 改用Hotpatch驱动

    * Config搭配Hotpatch即可引导

## Retina补丁使用
``` bash
ioreg -lw0 | grep IODisplayEDID | sed "/[^<]*</s///" | xxd -p -r | strings -6
B140HAN01.3 
```
查询您的显示屏型号是否符合本补丁，如果您的屏幕与我的屏幕VID不一致请自行修改VID和PID。
``` bash
/系统/资源库/Displays/Contents/Resources/Overrides/
```
修改完成后放入到此目录下并进行重启，可以达到MacBook系列原生开启Retina目的

# Hackintosh_E450C 

![截屏2019-11-1819 39 32](https://user-images.githubusercontent.com/9806325/69049782-9fe2a380-0a3b-11ea-9f03-f1b606f14729.png)
![截屏2019-11-1819 39 54](https://user-images.githubusercontent.com/9806325/69049792-a53fee00-0a3b-11ea-9a89-928444ba81a0.png)
![截屏2019-12-1820 40 34](https://user-images.githubusercontent.com/9806325/71087700-c67d3100-21d7-11ea-87ea-d85b8274c633.png)
![截屏2019-12-1301 12 28](https://user-images.githubusercontent.com/9806325/70765699-7a289000-1d96-11ea-9622-a27ab4a0580e.png)
![截屏2019-12-1301 13 05](https://user-images.githubusercontent.com/9806325/70765706-814f9e00-1d96-11ea-91a9-81d554eacf9d.png)
![截屏2019-12-1301 13 40](https://user-images.githubusercontent.com/9806325/70765711-86ace880-1d96-11ea-8695-66c2358474df.png)
![截屏2019-12-1301 20 13](https://user-images.githubusercontent.com/9806325/70765720-8dd3f680-1d96-11ea-973b-9e23018981ba.png)



E450C 黑苹果目前已经完成一下功能：

* IGPU Hotpatch驱动完成。

* HDAU 注入ID 27 完美进行切换，一切正常

* 亮度调整完成，FN+K降低亮度，FN+P提高亮度

* 注入Retina显示器

* LPC注入

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

# ***2.5寸USB-SATA硬盘笼***



## <u>视频链接:[B站视频--功能演示及介绍](https://www.bilibili.com/video/BV1YCw5eoERG/?vd_source=5028cf5016d7ed990ad38551eb4883cf)</u>

## 项目简介:

本项目采用JMS578作为usb-sata桥,JMB575端口倍增的方案,实现usb到多个sata硬盘的通信

## 项目参数:

DC12v电源输入,jms578内置3.3v的ldo和buck控制器,因此只需考虑jmb575的3.3v和1.2v电压供电.
12v输入进来后通过tps54335a降压到5v,再使用mp9148双路buck降压输出3.3和1.2给jmb575供电

但是考虑到tps54335a的封装有点不好焊接,隧将其改为了中兴zxdn10的电源模块
和主机间连接采用Type-B接口,相对来说更为牢固.接口速度为USB3.0 5Gpbs,但是usb后面级联sata的方案对于硬盘的随机读写性能有较大的损失,所以对此在意的可以考虑其他方案(机械硬盘用户无视此条)

![image.png](https://image.lceda.cn/oshwhub/pullImage/da8db4f8647841cdb107debac6505b63.png)

![Screenshot_2025-01-21-02-02-53-653_com.miui.galle.jpg](https://image.lceda.cn/oshwhub/pullImage/79a82d506c724422836df4d27d289a26.jpg)

![IMG_20250108_130723.jpg](https://image.lceda.cn/oshwhub/pullImage/4427e0c960e74686992918d71ac44c1d.jpg)

## 注意事项

1.在usb接口和dc电源接口的地方,请用钳子剪掉突出来的引脚,避免接触到硬盘.
2.先焊接电源部分,上电电压正常后再焊接芯片,以免烧毁芯片
3.jms578的晶振为30mhz,jmb575为25mhz
4.固件默认休眠时间为10min,若需更长时间或者关闭休眠,可以使用附件中的软件修改
5.由于最后一次修改工程后没能保存,所以附件中的ib0m和实际有区别,就是风扇接口位置不同.
6.电源功率的大小取决于你的硬盘功率
7.flash大部分都兼容,不确定就买p25d40h,便宜好用.

![image.png](https://image.lceda.cn/oshwhub/pullImage/847819558260480dad5023e42ae4ad5c.png)



## 组装流程

背后的散热风扇为12v5010的风扇,主板上有一颗电阻位,可以选择合适大小的电阻来调节风扇转速,一般情况下直接短接即可

![1737396598894.jpg](https://image.lceda.cn/oshwhub/pullImage/3cd789d3922c4763b5e3288fb526bebb.jpg)

## 实物图

![IMG_20250117_001012.jpg](https://image.lceda.cn/oshwhub/pullImage/019fda73d3d9429ea1527882594394f8.jpg)

![IMG_20250117_001045.jpg](https://image.lceda.cn/oshwhub/pullImage/a6f114a5ea5f4592ad035fae1db1bc11.jpg)

![IMG_20250117_001121.jpg](https://image.lceda.cn/oshwhub/pullImage/1efe802158cc4784a1533d1dd0c015d0.jpg)

![IMG_20250117_000405.jpg](https://image.lceda.cn/oshwhub/pullImage/ffd214ce9bcf4e009b82c4b899c49368.jpg)

![IMG_20250117_000419.jpg](https://image.lceda.cn/oshwhub/pullImage/84c1db9d41ea4a9c85ae98525bb871be.jpg)

![IMG_20250107_205519.jpg](https://image.lceda.cn/oshwhub/pullImage/e1942ecfca184c969d1d56d5abc83fe7.jpg)

![IMG_20250107_205544.jpg](https://image.lceda.cn/oshwhub/pullImage/69f3cbdddebb408ca55eb640aa7724b2.jpg)

![image.png](https://image.lceda.cn/oshwhub/pullImage/f9469a8aaa4e46eb9208911438cc24b8.png)
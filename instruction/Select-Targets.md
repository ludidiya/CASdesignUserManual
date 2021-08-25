---
author:
  name: LING ld
  link: 
  avatar: /static/avatar-girl.png

label: Select Targets
icon: multi-select
order: C
---

# 选择目标编辑区域

登录进入[CASdesign网站](http://124.71.187.96:8081/)，在`物种列表`页，搜索感兴趣的基因组，点击`编辑基因`后的弹框将提供两种选择目标编辑区的方式：

* :zap: 通过基因锁定编辑区域（Target genes）；

* :zap: 通过指定染色体编号、起始终止位点自定义编辑区域（Target genomic regions）

## Targrt genes

![！！后面需更新下这个图](../static/target-genes.png)

* 在`位置`检索框内，输入该基因组中的`基因名`或`locus tag`编号，检索确定编辑基因；

* 允许选择多个基因位点。


## Target genomic regions

![！！后面需更新下这个图](../static/target-genomic-regions.png)

* 输入`染色体编号`、`起始位点`和`终止位点`以确定编辑区域（注意：终止位点的坐标应大于等于起始位点的坐标）；

* 可以选设置区域的序列方向，当选择`负`时，程序会在可视化编辑界面展示原始序列的反向互补序列；

* 允许选择多个基因区间；


!!! **提示**

:sparkles: 1）两种方式均不允许选择重复的位点。

:sparkles: 2）允许两种方式混合使用，最终所有位点一并进入到可视化编辑界面。

!!!
---
author:
  name: LING ld
  link: 
  avatar: ../static/avatar-girl.png

label: Select Targets
icon: multi-select
order: C
---

# 选择目标编辑区域

登录进入[CASdesign网站](http://124.71.187.96:8081/)，在`物种列表`页，搜索感兴趣的基因组，点击`编辑基因`后，弹框将提供两种选择目标编辑区的方式：

* :zap: 通过搜索位点名称，包括基因名、Locus标签名、[表征位点名](/instruction/verified-Sites.md)等检索编辑区域（[Target named sites](/instruction/select-targets/#1-targrt-named-sites)）；

* :zap: 通过指定染色体编号、起始终止位点自定义编辑区域（[Target genomic regions](/instruction/select-targets/#2-target-genomic-regions)）。

## 1. Targrt named sites

![图1. 通过搜索功能片段名靶向编辑区。](../static/target-genes.png)

* 在`位置`检索框内，输入该基因组中的`基因名`、`locus`编号或[`表征位点名`](/instruction/verified-Sites.md)；

* 允许选择多个位点。


## 2. Target genomic regions

![图2. 自定义基因组区域。](../static/target-genomic-regions.png)

* 输入`染色体编号`、`起始位点`和`终止位点`以确定编辑区域；

* 可以选设置区域的序列方向，当选择`负`时，程序会在可视化编辑界面展示原始序列的反向互补序列；

* 允许设置多个基因区间。


!!! **提示**

:sparkles: 1）允许两种方式混合使用，最终所有位点一并进入到可视化编辑界面；

:sparkles: 2）自定义基因组区域时，终止位点的坐标应大于等于起始位点的坐标；

:sparkles: 3）自定义基因组区域时，边界坐标（同时考虑参数“目标区可视化侧翼链长度”和参数“编辑区同源左臂长度”）不能超出染色体区域范围。

!!!
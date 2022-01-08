---
author:
  name: LING ld
  link: 
  avatar: ../static/avatar-girl.png

label: Add New Genomes
icon: upload
order: B
---

# 新增基因组文件

![](../static/add-new-genomes.png)

登录[CASdesign网站](http://124.71.187.96:8081/)后，如果发现`菌株列表`中没有您感兴趣的物种，您可以在左侧菜单栏点击进入`新增物种`页面。点击`上传物种文件`，根据弹出框的提示，填写新增物种基因组文件的基本信息，主要包括：

* 物种分类：从物种分类列表中选择一个合适的，如`Bacteria`；

* 物种名：物种详细名称，可以有空格，如`copy_Saccharomyces cerevisiae S288CC`；

* 别名或简称：物种名的别名或简称，不可以有空格，如果有多个单词，请以下划线`_`分割，如`sacCer3`；

* 物种编号：物种编号，非必填项，用于区分比如菌株的不同株系，如`S288C`。同上，不允许空格，多个单词需以下划线`_`分割。

填写好物种基本信息后，上传物种对应的基因组`GenBank`文件（支持`gb`、`gbk`、`gbff`格式）。点击`确认`，等待后台程序解析基因组文件。

解析任务会将GenBank中注释的所有基因位点信息提取出来，以便用户通过[搜索基因名来靶向编辑区域](/instruction/select-targets/#targrt-genes)。此外，还将分析GenBank中各染色体的信息，以便用户通过[自定义染色体编号及起始终止位点靶向选择编辑区域](/instruction/select-targets/#target-genomic-regions)。

!!! **注意**

:sparkles: 1）`别名/简称_物种编号`（如`sacCer3_S288C`）两个字段的组合将作为程序唯一识别一个基因组文件的信息，当程序检测到您设置的名字与系统内已有的基因组`别名/简称_物种编号`重复时，会提示您。

!!!
---
author:
  name: LING ld
  link: 
  avatar: ../static/avatar-girl.png

label: Parameters
icon: code-square
order: D
---

# 参数设置

![图1. 进入参数设置界面。](../static/parameters/0-setParameters.png)

登录进入[CASdesign网站](http://124.71.187.96:8081/)，在`物种列表`页，首先进行如下操作：

* 选择感兴趣的基因组

* 在`位置选择`弹出框中选择感兴趣的编辑位点

* 在`位置选择`弹出框最下方，可选择使用CRISPR的`Cas9`或`Cpf1`编辑模式进行设计，同时可点击`参数设置`进行具体设置。

各参数的详细解释见下文。

## 1. General

![图2. 一般参数。](../static/parameters/1-general.png)

### 1）目标区域可视化侧翼链长度

![图2-1. 目标区域及两侧需额外展示的区域。](../static/parameters/FlankingVisual-light.png)

如上图所示，此参数定义了可视化交互编辑界面中，在目标位点（蓝色区域）两侧要额外显示的序列长度（橙色区域）。此参数是为了在交互编辑的时候，允许用户选择目标位点以外的区域进行基因敲除、基因插入/替换操作。

!!! **默认值**

1000 bp
!!!


### 2）编辑区同源左、右臂长度

![图2-2. 编辑区域同源修复左、右臂。](../static/parameters/1-2-homologyLestRight.png)

同源修复的左、右同源臂是发生同源双交换引入外源片段时必须的片段，是为了在引入外源片段时细胞发生同源重组修复过程中可以精准定位到特定位置并引入外源片段的引导者片段。它是在进行`基因敲除/替换`具体编辑操作的时候，`敲除/替换`区两侧的指定区间，需要根据该指定的同源区长度进行编辑区同源左右臂引物的计算。

!!! **默认值**

1000 bp
!!!


### 3）gRNA序列GC含量

设置gRNA序列GC含量（%）范围，筛选符合的gRNA。

!!! **默认值**

最小GC(%)含量：20%

最大GC(%)含量：80%
!!!

### 4）gRNA self-complementary

[CHOPCHOP](https://academic.oup.com/nar/article/47/W1/W171/5491735)算法中考虑了[Thyme等人的self-complementarity score研究](https://pubmed.ncbi.nlm.nih.gov/27282953/)，该方法计算了sgRNA内以及sgRNA与骨架之间潜在的4 bp茎数。因此，用户可以使用该选项选择避免具有自身互补性的sgRNA。

!!! **默认值**

-1 (no filter)
!!!


## 2. Cas9 or Cpf1

![图3. Cas9或Cpf1编辑模式下的可设定参数。](../static/parameters/2-cas9cpf1.png)

根据用户选择的不同基因编辑模式（Cas9或Cpf1），用户可对应分别设置：

* a. sgRNA长度：Cas9模式下默认长度为20 bp，Cpf1模式下默认长度为24 bp；

* b. PAM序列：Cas9模式下默认的PAM序列为`NGG`，Cpf1模式下默认是PAM序列为`TTCN`；

* c. gRNA效率算法（详情见下文）；

* d. gRNA载体引物（详情见下文）。

### 1）效率算法

CRISPR sgRNA可以按2个标准进行排名：

* a. 效率-特定sgRNA促进切割的可能性;

* b. 特异性-sgRNA结合脱靶位点的可能性。

根据实验研究，CHOPCHOP的初始版本提供了两个简单的效率指标:

* a. sgRNA的GC含量（理想的是介于40％和80％之间）；

* b. sgRNA是否在位置20处含有G。

自从CHOPCHOP发布以来，针对不同编辑模式下的gRNA效率评分已发展了越来越多的算法模型。使用这些方法，CHOPCHOP可以使用特定算法对每个sgRNA进行评分，在结果中，该分数被报告为“效率分数（Efficiency Score）”。

### 2）gRNA载体引物

Reider Apel A等人发表的[【A Cas9-based toolkit to program gene expression in Saccharomyces cerevisiae】](https://pubmed.ncbi.nlm.nih.gov/27899650/)一文中报道了27个高效的Cas9-sgRNA (pCut)质粒，可以整合到酵母1-16号染色体上23个特征良好的位点以使基因发生缺失或替换。

* [pCut质粒工具包可以从Addgene获取](https://www.addgene.org/kits/mukhopadhyay-pcut-toolkit/#kit-contents)

如下图，以基于CRISPR/Cas9原理对酵母基因组进行基因编辑，并使用[pCut Plasmid Toolkit](https://www.addgene.org/kits/mukhopadhyay-pcut-toolkit/#kit-contents)中[p426_Cas9_gRNA-ARS106a](https://www.addgene.org/browse/sequence/193424/)作为CRISPR基因编辑载体工具为例。在使用该软件进行gRNA设计时，需要指定gRNA在载体中所在位置两侧大约50-60bp（长度可调整）的序列，以最终输出gRNA引物来构建双链gRNA片段。

![图3-2. p426_Cas9_gRNA-ARS106a载体与gRNA-Forward、gRNA-Reverse引物示意图。](../static/parameters/2-2-Backbone-gRNA.png)

在本软件中，该设置在"参数设置——Cas9/Cpf1"界面下，如下图所示位置：

![图3-3. gRNA载体引物片段参数设置。](../static/parameters/2-3-gRNA-primer.png)

若设计得到的gRNA序列为`ACATCTCAAACAGAACATTG`，则结果页中得到的gRNA引物为：

* gRNA-Forward: `tcctcgctggcgccggctgggcaacaccttcgggtggcgaatgggactttACATCTCAAACAGAACATTG`

* gRNA-Reverse: `gttgataacggactagccttattttaacttgctatttctagctctaaaacCAATGTTCTGTTTGAGATGT`

小写部分是根据使用的不同载体，在参数设置处定义的gRNA在载体中所处位置两侧片段（方向均为5'->3'），大写部分是gRNA片段。

!!! **注意**

* 软件此处默认参数是使用p426_Cas9_gRNA-ARS106a载体时的引物片段，需要根据实际设计原理（Cas9或Cpf1）所用的载体工具来更新参数。
!!!


## 3. Primers

![图4. 敲除、插入/替换引物设计时可设定参数。](../static/parameters/3-primer.png)

### 1）敲除引物参数设置

![图4-1. 敲除编辑时引物计算规则。](../static/parameters/3-1-knockoutPrimers.png)

* a. 结果页中，敲除的引物名为`编辑位点名-repair-F`和`编辑位点名-repair-R`。其中，`F`和`R`分别表示`Forward`和`Reverse`；

* b. 默认情况下，`F`的组成为引物总碱基88个（可通过`product size`更改），编辑位置后20-28 bp序列内（可通过`primer size`更改）Tm在55-60度（可通过`primer TM`更改）之间的序列（如不能达到该要求，直接取后25 bp序列）；

* c. 默认情况下，`R`的组成为，编辑位置的后88个序列（可通过`product size`更改）。


### 2）插入片段引物参数设置

![图4-2. 插入/替换编辑时引物计算规则。](../static/parameters/3-2-knockoutReplacePrimers.png)

* a. 结果页中，插入/替换的引物名为：`编辑位点名-HoL/R-F/R`，`Frag1-F/R`，`Frag2-F/R`……`Frag(n)-F/R`。其中，`n`为用户输入的片段数；

* b. HoL，同源左臂：默认取选定的区域前1000个序列（由`General`下`编辑区同源左臂长度`控制）。HoL-F为开始的30 bp内（可通过`primer size`更改）Tm在55-60度（可通过`primer TM`更改）的序列（如不能达到该要求，直接取后25个序列） ，HoL-R为结束的30 bp内Tm在55-60度的序列（如不能达到该要求，直接取后25个序列） +片段1前60 bp（可通过`size overhang in next insert`更改）；

* c. HoR，同源右臂：默认取选定的区域后1000个序列（由`General`下`编辑区同源右臂长度`控制）。HoR-F为片段n的最后60 bp+开始的30 bp内Tm在55-60度的序列（如不能达到该要求，直接取后25个序列）序列，HoR-R为结束的30 bp内Tm在55-60度的序列；

* d. 片段1：Frag1-F为开始的30 bp内Tm在55-60度的序列，Frag1-R为结束的30 bp内Tm在55-60度的序列（如不能达到该要求，直接取后25个序列） +片段2前60 bp；

* e. 片段2：Frag2-F为开始的30 bp内Tm在55-60度的序列，Frag2-R为结束的30 bp内Tm在55-60度的序列（如不能达到该要求，直接取后25个序列） +片段3前60 bp；

* f. 片段3：Frag3-F为开始的30 bp内Tm在55-60度的序列，Frag3-R为结束的30 bp内Tm在55-60度的序列（如不能达到该要求，直接取后25个序列） +片段4前60 bp；

* g. 片段4：Frag4-F为开始的30 bp内Tm在55-60度的序列，Frag4-R为结束的30 bp内Tm在55-60度的序列；

* h. …………

* i. 如此类推，最后一个片段的规则为取开始的30 bp内Tm在55-60度的序列为F，结束的30 bp内Tm在55-60度的序列为R。

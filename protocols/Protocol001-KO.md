---
author:
  name: WU yl
  link: 
  avatar: ./static/avatar-girl.png

label: Protocol for Knock Out
icon: checklist
order: A
---

# 基因敲除实验流程

## 一、引物订购

:shopping_trolley:订购以下两段引物：

| **引物名**   	 | **序列（5'-> 3'）** |
| :---:          | :--- |
| pCUT-F         |  gttttagagctagaaatagcaagttaaaataaggc  |
| pCUT-R         |   aaagtcccattcgccaccc   |

## 二、PCR获得线性化pCUT骨架

**1）第一步：** 准备PCR反应体系

| **组份** | **体积（μL）** |
| :---: | :---: |
| 2×Phanta Max Master Mix | 25 |
| pCUT-F | 2 |
| pCUT-R | 2 |
| pCUT模版 | 0.25（约20-50ng） |
| H2O | 20.75 |
| **总体积** | **50** |

!!!primary 备注：
pCUT模版可以为任意一个现有的pCUT载体
!!!

**2）第二步：** 进行如下PCR反应

|**步骤** |	**温度（°C）** |	**时间** |  **备注** |
|:---:|:---:|:---:|:---:|
|1 |	95 |	3min	| |
|2<br>3<br>4 |	95<br>52<br>72 | 15s<br>15s<br>3min	 | <br>35个循环<br><br> |
|5 |	72 |	5min	| |
|6 |	16 |	∞	| |

<table width="750" border="1">
	<tr>
		<td align="center"><b>步骤</b></td>
		<td align="center"><b>温度（°C）</b></td>
		<td align="center"><b>时间</b></td>
		<td align="center"><b>备注</b></td>
	</tr>
	<tr>
		<td align="center">1</td>
		<td align="center">95</td>
		<td align="center">3min</td>
		<td align="center"></td>
	</tr>
	<tr>
		<td align="center">2</td>
		<td align="center">95</td>
		<td align="center">15s</td>
		<td align="center" rowspan="3">35个循环</td>
	</tr>
	<tr>
		<td align="center">3</td>
		<td align="center">52</td>
		<td align="center">15s</td>
	</tr>
	<tr>
		<td align="center">4</td>
		<td align="center">72</td>
		<td align="center">3min</td>
	</tr>
	<tr>
		<td align="center">5</td>
		<td align="center">72</td>
		<td align="center">5min</td>
		<td align="center"></td>
	</tr>
	<tr>
		<td align="center">6</td>
		<td align="center">16</td>
		<td align="center">∞</td>
		<td align="center"></td>
	</tr>
</table>


**3）第三步：** PCR反应结束后，直接在PCR反应体系中加入1μL的DpnI限制性内切酶（NEB）在37摄氏度下消化30-60分钟


**4）第四步：** 消化结束后，使用1%的琼脂糖核酸凝胶进行电泳验证


**5）第五步：** 验证线性化骨架大小正确后，直接进行PCR产物纯化，浓度测定，线性化骨架片段待用



## 三、构建双链gRNA片段

**1）第一步：** 使用CASDesign进行gRNA引物设计

**2）第二步：** 把gRNA引物稀释到终浓度为10μM的工作浓度

**3）第三步：** 准备PCR反应体系

| **组份** | **体积（μL）** |
| :---: | :---: |
| 2×Phanta Max Master Mix | 25 |
| pCUT-F | 2 |
| pCUT-R | 2 |
| H2O | 21 |
| **总体积** | **50** |

**4）第四步：** 进行如下PCR反应

|**步骤** |	**温度（°C）** |	**时间** |  **备注** |
|:---:|:---:|:---:|:---:|
|1 |	95 |	3min	| |
|2<br>3<br>4 |	95<br>52<br>72 | 15s<br>15s<br>3min	 | <br>35个循环<br><br> |
|5 |	72 |	5min	| |
|6 |	16 |	∞	| |

**5）第五步：** PCR完成后进行产物纯化，测定浓度，该gRNA片段待用

## 四、构建修复DNA片段

**第一步：** 使用CASDesign进行修复DNA片段引物设计

**第二步：** 如步骤3，构建修复DNA片段

## 五、酿酒酵母转化

**第一步：** 酵母过夜活化后转接至约50 mL YPD培养基中，初始OD调节至约为0.2

**第二步：** 30℃ 220rpm培养至OD在0.6-1.0之间

**第三步：** 将菌液转入无菌离心管中，3000rpm离心5min后弃去YPD培养基

**第四步：** 重悬于40mL无菌水中，3000rpm离心5min后去上清

**第五步：** 重悬细胞于10mL 0.1M LiAc中，用微量移液器轻轻混匀，3000rpm离心5min后去上清

**第六步：** 重悬细胞于400 uL的0.1M LiAc中，轻轻混匀

**第七步：** 吸取50uL样品加到标记的无菌离心管中，5000rpm，离心60s

**第八步：** 去除LiAc， 加入240μL 50% PEG3350，混匀后加入36μL 1M LiAc，加入5μL 10mg/mL单链鱼精DNA（100℃煮沸5min后迅速置于冰上）

**第九步：** 加入步骤3中的gRNA片段DNA（0.1-10ug），步骤4中的修复DNA片段（0.1-10ug），步骤2中的线性化pCUT骨架（约300-500ng），最后加入无菌水至体积为70μL

**第十步：** 混匀，置30℃保温30 min，置42℃热击25min

**第十一步：** 5000rpm，60s离心，除去转化液，重悬细胞于1mL无菌水

**第十二步：** 离心去上清，加入无菌水，涂布在与所用pCUT线性化骨架相应营养缺陷型平板上


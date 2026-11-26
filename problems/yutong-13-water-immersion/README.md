# 第十三届宇瞳杯 · 水浸物镜

使用 785、810、850 nm 三个等权波长，从空气侧无穷远反向成像至浸水侧的 K5 盖玻片。纯水层 0.510 mm，盖玻片 0.17 mm，采样像面设在盖玻片之后的接触面。焦距按显微物镜空气侧等效焦距报告，并在数据中保留软件输出的像方焦距。 [官方题面](https://cos.hdu.edu.cn/_upload/article/files/f8/b5/302410984f48a2fb1aa51a218265/5da01fea-82ab-43a6-9365-f3185b71f3c1.pdf#page=4) · [纯水色散](https://doi.org/10.1364/AO.46.003811)

## 处方与复验

以公开物镜结构为起点，重设浸液、玻璃、近轴焦距、光阑和工作距离，优化曲率、轴向间隔和偶次非球面。优化同时约束各场单色波前与 785、810、850 nm 三波长主光线的最大像点间距。冻结处方在 Optiwork v1.2.2 重开后转为 Zemax 原生处方，逐面核对材料、半径、厚度、非球面系数和孔径。每个波长在 41 场追迹，在同一固定像面扣除活塞与倾斜。两边逐场最大的 PV 差为 7.8e-06 波。 [初始结构出处](https://patents.google.com/patent/JP2014048342A/en)

| 指标 | 赛题 | 复算值 |
| --- | ---: | ---: |
| 空气侧等效焦距（mm） | 4.75 | 4.75021 |
| 810 nm 边场像高（mm） | 0.707 | 0.706764 |
| 轴上最小实测 NA | ≥ 0.9 | 0.902935 |
| Optiwork 最大波前 PV（波） | < 0.25 | 0.213053 |
| Zemax 最大波前 PV（波） | < 0.25 | 0.213053 |
| 水侧最大主光线角（°） | < 2 | 0.507458 |
| 总长（mm） | < 50.8 | 50.6171 |
| 最大净口径（mm） | ≤ 25.4 | 15.7566 |
| 最大绝对畸变（%） | < 5 | 3.22561 |
| 三波长最大场曲（µm） | < 25 | 0.308936 |
| 实光线轴向色差（µm） | < 3 | 0.321091 |
| 垂轴色差（µm） | < 1 | 0.827257 |
| 最低镀膜功率透过率估算（%） | > 85 | 86.6617 |

## 几何与透过率模型

成品边界按每片独立锥边建模，按全口径核对实体、光阑和端点通光。总透过率使用三波长实光线最大入射角与最长光程、候选膜堆和厂家玻璃吸收记录进行保守估算。膜层色散采用名义折射率，波前表按未附加膜层的光学面计算。实物透过率、成膜引入的波前相位、公差、倒角和装调仍待测量。 [膜材资料](https://www.emdgroup.com/business-specifics/performance-materials/Optoelectronics/us/Patinal-Evaporation-Materials-DE-US.pdf)

## 原生处方和验收数据

在 Optiwork 导入 [YUTONGWATER.agf](YUTONGWATER.agf)，或把它加入 Zemax 的 `Glasscat`，再打开对应处方。

- [Optiwork 处方](lens.owx) · [Optiwork 复验](optiwork.json)
- [Zemax 处方](lens.zmx) · [Zemax 复验](zemax.json)
- [验收表](acceptance.json) · [实光线包络](ray-envelope.json) · [膜堆与透过率估算](transmission.json)

## 多色 MTF

三波长等权、同一固定像面，在轴上、半视场和边场复算。Optiwork 使用 512 × 512 瞳面网格的标量 FFT。Zemax 使用 128 × 128 瞳面网格、256 × 256 像面网格的 Huygens 法，像面步长 0.1 µm。两处方比较采用相同频率。 [Ansys MTF 方法说明](https://optics.ansys.com/hc/en-us/articles/42661772706835-Methods-for-analyzing-MTF-in-OpticStudio)

| 边场频率（lp/mm） | 原版 Zemax 子午 / 弧矢 | 新版 Optiwork 子午 / 弧矢 | 新版 Zemax 子午 / 弧矢 |
| ---: | ---: | ---: | ---: |
| 500 | 0.230 / 0.622 | 0.455 / 0.667 | 0.442 / 0.626 |
| 1000 | 0.174 / 0.383 | 0.099 / 0.420 | 0.081 / 0.399 |

全谱垂轴色差从 1.0997 µm 降到 0.8273 µm。边场 500 lp/mm 的子午对比度明显提高，1000 lp/mm 的子午对比度仍低。多色 MTF 作为成像诊断附列，赛题按第 4 页所列指标验收。

- [Optiwork 多色 MTF](mtf-optiwork.json) · [Zemax 多色 MTF](mtf-zemax.json)

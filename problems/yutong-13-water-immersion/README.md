# 第十三届宇瞳杯 · 水浸物镜

使用 785、810、850 nm 三个等权波长，从空气侧无穷远反向成像至浸水侧的 K5 盖玻片。纯水层 0.551 mm，盖玻片 0.17 mm，采样像面设在盖玻片之后的接触面。焦距按显微物镜空气侧等效焦距报告，并在数据中保留软件输出的像方焦距。 [官方题面](https://cos.hdu.edu.cn/_upload/article/files/f8/b5/302410984f48a2fb1aa51a218265/5da01fea-82ab-43a6-9365-f3185b71f3c1.pdf#page=4) · [纯水色散](https://doi.org/10.1364/AO.46.003811)

## 处方与复验

以公开物镜结构为起点，重设浸液、玻璃、近轴焦距、光阑和工作距离，优化曲率、轴向间隔和偶次非球面。优化同时约束各场单色波前与 785、810、850 nm 三波长主光线的最大像点间距。冻结处方在 Optiwork v1.2.2 重开后转为 Zemax 原生处方，逐面核对材料、半径、厚度、非球面系数和孔径。每个波长在 41 场追迹，在同一固定像面扣除活塞与倾斜。两边逐场最大的 PV 差为 3.4e-07 波。 [初始结构出处](https://patents.google.com/patent/JP2014048342A/en)

| 指标 | 赛题 | 复算值 |
| --- | ---: | ---: |
| 空气侧等效焦距（mm） | 4.75 | 4.74965 |
| 810 nm 边场像高（mm） | 0.707 | 0.706958 |
| 轴上最小实测 NA | ≥ 0.9 | 0.904513 |
| Optiwork 最大波前 PV（波） | < 0.25 | 0.0890218 |
| Zemax 最大波前 PV（波） | < 0.25 | 0.089022 |
| 水侧最大主光线角（°） | < 2 | 1.04539 |
| 总长（mm） | < 50.8 | 50.4596 |
| 最大净口径（mm） | ≤ 25.4 | 15.8362 |
| 最大绝对畸变（%） | < 5 | 3.57952 |
| 三波长最大场曲（µm） | < 25 | 0.189548 |
| 实光线轴向色差（µm） | < 3 | 0.066494 |
| 垂轴色差（µm） | < 1 | 0.0813986 |
| 最低镀膜功率透过率估算（%） | > 85 | 85.9567 |

## 几何与透过率模型

成品边界按每片独立锥边建模，按全口径核对实体、光阑和端点通光。总透过率使用三波长实光线最大入射角与最长光程、候选膜堆和厂家玻璃吸收记录进行保守估算。膜层色散采用名义折射率，波前表按未附加膜层的光学面计算。实物透过率、成膜引入的波前相位、公差、倒角和装调仍待测量。 [膜材资料](https://www.emdgroup.com/business-specifics/performance-materials/Optoelectronics/us/Patinal-Evaporation-Materials-DE-US.pdf)

## 原生处方和验收数据

在 Optiwork 导入 [YUTONGWATER.agf](YUTONGWATER.agf)，或把它加入 Zemax 的 `Glasscat`，再打开对应处方。

- [Optiwork 处方](lens.owx) · [Optiwork 复验](optiwork.json)
- [Zemax 处方](lens.zmx) · [Zemax 复验](zemax.json)
- [验收表](acceptance.json) · [实光线包络](ray-envelope.json) · [膜堆与透过率估算](transmission.json)

## 多色 MTF

三波长等权、同一固定像面，在 11 个视场复算。Optiwork 使用 256 × 256 瞳面网格的标量 FFT。Zemax 使用 128 × 128 瞳面网格、256 × 256 像面网格的 Huygens 法，像面步长 0.1 µm。两处方比较采用相同频率。 [Ansys MTF 方法说明](https://optics.ansys.com/hc/en-us/articles/42661772706835-Methods-for-analyzing-MTF-in-OpticStudio)

| 边场频率（lp/mm） | 原版 Zemax 子午 / 弧矢 | 新版 Optiwork 子午 / 弧矢 | 新版 Zemax 子午 / 弧矢 |
| ---: | ---: | ---: | ---: |
| 500 | 0.442 / 0.626 | 0.707 / 0.704 | 0.652 / 0.652 |
| 1000 | 0.081 / 0.399 | 0.441 / 0.441 | 0.416 / 0.416 |

第 1 面后的镜片由 `SCHOTT:N-LAF7` 换为 `OHARA:S-NBH53V`，第 22 面后的镜片由 `SCHOTT:LITHOSIL-Q` 换为 `CDGM:H-FK71A`，并重新优化曲率、厚度和非球面。

在 11 场、750–1150 lp/mm 内，Zemax 多色子午 MTF 最差值由 0.067 升至 0.353，Optiwork 复算为 0.364。全谱垂轴色差为 0.0814 µm。

名义实体中，光学面共同半径内的最小玻璃轴向厚度为 0.228 mm，最小镜片净距 0.109 mm，最短锥边轴向跨度 0.203 mm。锥边跨度用于几何检查，实际倒角、承靠、装调公差、长期浸水和成膜后波前仍需工艺或样件验证。 [工程复核](engineering-review.json) · [优化前后 MTF 曲线](mtf-comparison.png)

边场扰动试算中，K5 厚度变化 ±5 µm 时，固定工作距离的带内最差 MTF 低于 0.01。将水层厚度反向调整约 4.25 µm 后，可恢复到 0.355 以上。镜组需有轴向调焦能力。 [水层与盖玻片敏感性](focus-sensitivity.json)

11 场、750–1150 lp/mm 内，Zemax 子午与弧矢最大差值为 0.0056，两向共同最低值为 0.353。按同轴上 NA、等权三波段的均匀圆瞳衍射基准，1000 lp/mm 的参考值约为 0.447。折射界面与瞳面振幅采用标量模型。 [圆瞳 MTF 参考](https://www.microscopyu.com/microscopy-basics/modulation-transfer-function)

归档还包含 12 组组装扰动重放和光学曲面之间的最短物理厚度计算。组装误差来自工程试算的假设分布，重放覆盖一个子午方向。 [组装扰动](assembly-tolerance.json) · [最短厚度复核](meridional-review.json)

- [Optiwork 多色 MTF](mtf-optiwork.json) · [Zemax 多色 MTF](mtf-zemax.json)

# IODC 2017 百年镜头

题目要求在系统内保留 100 mm 固定模块，由 10 mm 厚的平板、两颗 Ø40 mm 球镜和两个 5 mm 空气隙组成。系统使用 SCHOTT N-BK7、587.56 nm 单色光和固定平像面。无渐晕时，所有视场的 RMS 波前误差须不超过 0.070 波。评分是两颗球镜上最大轴上边缘光线高度与最大边缘视场主光线高度的乘积。理论上限为 400 mm²。 [赛事题面](https://iodc.info/2016/09/2017-lens-design-problem/) · [赛事 FAQ](https://iodc.info/2016/09/2017-frequently-asked-and-unasked-questions/)

## 处方与复验

用 Optiwork v1.2 建立固定模块，在前方放置实体光阑，在模块后加一片 N-BK7 正透镜，搜索入瞳、半视场和固定像面位置。两颗球镜各用半径为 ±20 mm、轴厚 40 mm 的两个半球面表示。光学清孔半径为 19.9999 mm，以避开球面在赤道处的数值奇点。

| 项目 | Optiwork v1.2 | Zemax OpticStudio 2022 R2.02 |
| --- | ---: | ---: |
| 31 个视场中的最大 RMS 波前误差（波） | 0.0699818107 | 0.0699818108 |
| 评分（mm²） | 1.8316194870 | 1.8316194870 |
| 采样瞳孔的内部与边界光线 | 全通光 | 全通光 |

复验采用同一份处方，入瞳直径为 2.650 mm，半视场为 2.5834°，末面顶点到像面的距离为 37.961056 mm。两套软件都去除活塞和倾斜并保留离焦。Optiwork 使用 28 × 96 的面积积分采样，Zemax 使用 24 环的原生 RWCE 操作数。球镜上的评分光线由两套软件独立追迹。

这是一份达到题面约束的基础解。相对理论上限，评分仍有很大提升空间。制造评估限于 Optiwork 中的名义同轴几何。

## 文件

- [Optiwork 原生处方](centennial.owx)
- [Zemax 原生处方](centennial.zmx)
- [Optiwork 波前、瞳孔和几何结果](optiwork-verification.json)
- [Zemax 与 Optiwork 逐场对照](zemax-comparison.json)
